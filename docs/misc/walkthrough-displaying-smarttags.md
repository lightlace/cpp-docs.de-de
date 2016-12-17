---
title: "Exemplarische Vorgehensweise: Anzeigen von Smarttags"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Editoren [Visual Studio SDK], neu – Smarttags"
ms.assetid: 10bb4f69-b259-41f0-b91a-69b04385d9a5
caps.latest.revision: 31
caps.handback.revision: "31"
manager: "douge"
---
# Exemplarische Vorgehensweise: Anzeigen von Smarttags
Smarttags sind veraltet und wurden gegen Glühbirnen ausgetauscht. Siehe [Exemplarische Vorgehensweise: Anzeigen von Glühbirne Vorschläge](../Topic/Walkthrough:%20Displaying%20Light%20Bulb%20Suggestions.md).  
  
 Smarttags sind Tags für Text, die erweitert werden können, um eine Reihe von Aktionen anzuzeigen. Beispielsweise wird in einem Visual Basic\- oder Visual C\#\-Projekt eine rote Linie unter einem Wort angezeigt, wenn Sie einen Bezeichner \(z. B. Variablenname\) umbenennen. Wenn Sie den Mauszeiger über die Unterstreichung bewegen, wird eine Schaltfläche in der Nähe des Zeigers angezeigt. Wenn Sie auf die Schaltfläche klicken, wird eine empfohlene Aktion angezeigt, z. B. **IsRead in IsReady umbenennen**. Wenn Sie auf die Aktion klicken, werden alle Verweise auf **IsRead** im Projekt in **IsReady** umbenannt.  
  
 Obwohl Smarttags Bestandteil der IntelliSense\-Implementierung im Editor sind, können Sie Smarttags implementieren, indem Sie eine Unterklasse für <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag> erstellen und dann die Schnittstellen <xref:Microsoft.VisualStudio.Text.Tagging.ITagger`1> und <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider> implementieren.  
  
> [!NOTE]
>  Andere Arten von Tags können auf ähnliche Weise implementiert werden.  
  
 Die folgende exemplarische Vorgehensweise veranschaulicht, wie Sie ein Smarttag erstellen, das für das aktuelle Wort angezeigt wird und zwei empfohlene Aktionen beinhaltet: **In Großbuchstaben umwandeln** und **In Kleinbuchstaben umwandeln**.  
  
## Vorbereitungsmaßnahmen  
 Um dieser exemplarischen Vorgehensweise folgen zu können, müssen Sie das Visual Studio SDK installieren. Weitere Informationen finden Sie unter [Visual Studio SDK](../Topic/Visual%20Studio%20SDK.md).  
  
## Erstellen eines MEF\-Projekts \(Managed Extensibility Framework\)  
  
#### So erstellen Sie ein MEF\-Projekt  
  
1.  Erstellen Sie ein Editorklassifiziererprojekt. Nennen Sie die Projektmappe `SmartTagTest`.  
  
2.  Öffnen Sie im VSIX\-Manifest\-Editor die Datei "source.extension.vsixmanifest".  
  
3.  Stellen Sie sicher, dass der Abschnitt **Objekte** einen `Microsoft.VisualStudio.MefComponent`\-Typ enthält, die **Quelle** auf `A project in current solution` und das **Projekt** auf SmartTagTest.dll festgelegt ist.  
  
4.  Speichern und schließen Sie die Datei "source.extension.vsixmanifest".  
  
5.  Fügen Sie den folgenden Verweis auf das Projekt hinzu, und legen Sie **CopyLocal** auf `false` fest:  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
6.  Löschen Sie die vorhandenen Klassendateien.  
  
## Implementieren eines Taggers für Smarttags  
  
#### So implementieren Sie einen Tagger für Smarttags  
  
1.  Fügen Sie eine Klassendatei hinzu, und nennen Sie sie `TestSmartTag`.  
  
2.  Fügen Sie die folgenden Importe hinzu:  
  
     [!CODE [VSSDKSmartTagTest#1](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#1)]  
  
3.  Fügen Sie eine Klasse namens `TestSmartTag` hinzu, die von <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag> erbt.  
  
     [!CODE [VSSDKSmartTagTest#2](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#2)]  
  
4.  Fügen Sie einen Konstruktor für diese Klasse hinzu, der den Basiskonstruktor mit einem <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> von <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> aufruft, wodurch der erste Buchstabe eines Worts mit einer blauen Linie unterstrichen wird. \(Bei Verwendung von <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> wird der letzte Buchstabe des Worts rot unterstrichen.\)  
  
     [!CODE [VSSDKSmartTagTest#3](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#3)]  
  
5.  Fügen Sie eine Klasse mit dem Namen `TestSmartTagger` hinzu, die von <xref:Microsoft.VisualStudio.Text.Tagging.ITagger`1> vom Typ `TestSmartTag` erbt und <xref:System.IDisposable> implementiert.  
  
     [!CODE [VSSDKSmartTagTest#4](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#4)]  
  
6.  Fügen Sie der Taggerklasse die folgenden privaten Felder hinzu:  
  
     [!CODE [VSSDKSmartTagTest#5](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#5)]  
  
7.  Fügen Sie einen Konstruktor hinzu, der die privaten Felder festlegt und das <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged>\-Ereignis abonniert.  
  
     [!CODE [VSSDKSmartTagTest#6](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#6)]  
  
8.  Implementieren Sie <xref:Microsoft.VisualStudio.Text.Tagging.ITagger`1.GetTags*>, damit das Tag für das aktuelle Wort erstellt wird. \(Mit dieser Methode wird auch die private Methode `GetSmartTagActions` aufgerufen, die zu einem späteren Zeitpunkt erläutert wird.\)  
  
     [!CODE [VSSDKSmartTagTest#7](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#7)]  
  
9. Fügen Sie eine `GetSmartTagActions`\-Methode hinzu, um die Smarttag\-Aktionen einzurichten. Die Aktionen selbst werden in späteren Schritten implementiert.  
  
     [!CODE [VSSDKSmartTagTest#8](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#8)]  
  
10. Deklarieren Sie das `SmartTagsChanged`\-Ereignis.  
  
     [!CODE [VSSDKSmartTagTest#9](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#9)]  
  
11. Implementieren Sie den `OnLayoutChanged`\-Ereignishandler, um das `TagsChanged`\-Ereignis auszulösen, wodurch <xref:Microsoft.VisualStudio.Text.Tagging.ITagger`1.GetTags*> aufgerufen wird.  
  
     [!CODE [VSSDKSmartTagTest#10](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#10)]  
  
12. Implementieren Sie die <xref:System.IDisposable.Dispose*>\-Methode, damit das Abonnement des <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged>\-Ereignisses aufgehoben wird.  
  
     [!CODE [VSSDKSmartTagTest#11](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#11)]  
  
## Implementieren des Anbieters des Smarttag\-Taggers  
  
#### So implementieren Sie den Anbieter des Smarttag\-Taggers  
  
1.  Fügen Sie eine Klasse namens `TestSmartTagTaggerProvider` hinzu, die von <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider> erbt. Exportieren Sie sie mit dem <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "Text", dem <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> Before \= "Default" und dem <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute><xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>.  
  
     [!CODE [VSSDKSmartTagTest#12](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#12)]  
  
2.  Importieren Sie <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> als Eigenschaft.  
  
     [!CODE [VSSDKSmartTagTest#13](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#13)]  
  
3.  Implementieren Sie die <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger*>\-Methode.  
  
     [!CODE [VSSDKSmartTagTest#14](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#14)]  
  
## Implementieren von Smarttag\-Aktionen  
  
#### So implementieren Sie Smarttag\-Aktionen  
  
1.  Erstellen Sie zwei Klassen, die erste mit dem Namen `UpperCaseSmartTagAction` und die zweite mit dem Namen `LowerCaseSmartTagAction`. Beide Klassen implementieren <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction>.  
  
     [!CODE [VSSDKSmartTagTest#15](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#15)]  
  
     [!CODE [VSSDKSmartTagTest#16](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#16)]  
  
 Beide Klassen sind bis auf eine Ausnahme identisch: Die eine ruft <xref:System.String.ToUpper*> und die andere <xref:System.String.ToLower*> auf. In den folgenden Schritten wird nur die Klasse für die Umwandlung in Großbuchstaben behandelt; Sie müssen aber beide Klassen implementieren. Verwenden Sie diese Schritte als Muster für die Implementierung der Aktion zur Umwandlung in Kleinbuchstaben.  
  
1.  Deklarieren Sie einen Satz privater Felder.  
  
     [!CODE [VSSDKSmartTagTest#17](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#17)]  
  
2.  Fügen Sie einen Konstruktor hinzu, der die Felder festlegt.  
  
     [!CODE [VSSDKSmartTagTest#18](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#18)]  
  
3.  Implementieren Sie die Eigenschaften wie folgt:  
  
     [!CODE [VSSDKSmartTagTest#19](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#19)]  
  
4.  Implementieren Sie die <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction.Invoke*>\-Methode, indem Sie den Text im Bereich durch entsprechende Großbuchstaben ersetzen.  
  
     [!CODE [VSSDKSmartTagTest#20](../CodeSnippet/VS_Snippets_VSSDK/vssdksmarttagtest#20)]  
  
## Erstellen und Testen des Codes  
 Um diesen Code zu testen, erstellen Sie die Projektmappe "SmartTagTest", und führen Sie sie in der experimentellen Instanz aus.  
  
#### So erstellen Sie die Projektmappe "SmartTagTest" und testen den Code  
  
1.  Erstellen Sie die Projektmappe.  
  
2.  Wenn Sie dieses Projekt im Debugger ausführen, wird eine zweite Instanz von Visual Studio instanziiert.  
  
3.  Erstellen Sie eine Textdatei, und geben Sie Text ein.  
  
     Unter dem ersten Buchstaben des ersten Worts im Text sollte eine blaue Linie angezeigt werden.  
  
4.  Bewegen Sie den Zeiger über die blaue Linie.  
  
     Neben dem Zeiger sollte eine Schaltfläche angezeigt werden.  
  
5.  Wenn Sie auf die Schaltfläche klicken, sollten zwei empfohlene Aktionen angezeigt werden: **In Großbuchstaben umwandeln** und **In Kleinbuchstaben umwandeln**. Wenn Sie auf die erste Aktion klicken, sollte der gesamte Text im aktuellen Wort in Großbuchstaben umgewandelt werden. Wenn Sie auf die zweite Aktion klicken, sollte der gesamte Text im aktuellen Wort in Kleinbuchstaben umgewandelt werden.  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Verknüpfen eines Inhaltstyps mit Erweiterung](../Topic/Walkthrough:%20Linking%20a%20Content%20Type%20to%20a%20File%20Name%20Extension.md)