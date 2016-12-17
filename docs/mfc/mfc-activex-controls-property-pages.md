---
title: "MFC-ActiveX-Steuerelemente: Eigenschaftenseite"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPageDialog-Klasse"
  - "DDP_-Funktionen"
  - "DoDataExchange-Methode"
  - "MFC-ActiveX-Steuerelemente, Eigenschaften"
  - "MFC-ActiveX-Steuerelemente, Eigenschaftenseiten"
  - "OLEIVERB_PROPERTIES"
  - "Eigenschaftenseiten, MFC-ActiveX-Steuerelemente"
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Eigenschaftenseite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Eigenschaftenseiten können Benutzer die Eigenschaften von ActiveX\-Steuerelementen anzeigen und ändern.  Der Zugriff auf diese Eigenschaften erfolgt über ein Dialogfeld für die Steuerelementeigenschaften. Dieses enthält eine oder mehrere Eigenschaftenseiten, die eine angepasste grafische Oberfläche zum Anzeigen und Bearbeiten der Steuerelementeigenschaften bereitstellen.  
  
 Eigenschaftenseiten für ActiveX\-Steuerelemente werden auf zwei Arten angezeigt:  
  
-   Wenn das Eigenschaftenverb des Steuerelements \(**OLEIVERB\_PROPERTIES**\) aufgerufen wird, wird das Steuerelement ein modales Eigenschaftendialogfeld, das den Eigenschaftenseiten des Steuerelements enthält.  
  
-   Der Container kann ein eigenes nicht modales Dialogfeld anzeigen, das den Eigenschaftenseiten des ausgewählten Steuerelements anzeigt.  
  
 Das Eigenschaftendialogfeld \(demonstriert in der folgenden Abbildung\) besteht aus einem Bereich zum Anzeigen der aktuellen, Eigenschaftenseite der Registerkarten zum Umschalten zwischen Eigenschaftenseiten und der Auflistung Schaltflächen, häufige Aufgaben wie Schließen des Projektdialogfelds ausführen, bricht alle vorgenommenen Änderungen ab, oder sofort anwendet Änderungen am ActiveX\-Steuerelement.  
  
 ![Eigenschaftendialogfeld für Circ3](../mfc/media/vc373i1.png "vc373I1")  
Eigenschaften\-Dialogfeld  
  
 Dieser Artikel enthält die Themen, die zur Verwendung von Eigenschaftenseiten in einem ActiveX\-Steuerelement verknüpft werden.  Dazu gehören:  
  
-   [Implementieren der Standardeigenschaftsseite eines ActiveX\-Steuerelements](#_core_implementing_the_default_property_page)  
  
-   [Hinzufügen von Steuerelementen zu einer Eigenschaftenseite](#_core_adding_controls_to_a_property_page)  
  
-   [Anpassen der DoDataExchange\-Funktion](#_core_customizing_the_dodataexchange_function)  
  
 Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX\-Steuerelement, finden Sie:  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 Informationen über die Verwendung von Eigenschaftenblättern in einer MFC\-Anwendung anders ein ActiveX\-Steuerelement, finden Sie unter [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).  
  
##  <a name="_core_implementing_the_default_property_page"></a> Implementieren der Standardeigenschafts\-Seite  
 Wenn Sie den ActiveX\-Steuerelement\-Assistenten verwenden, um das Steuerelementprojekt erstellen, stellt der ActiveX\-Steuerelement\-Assistent eine Standardeigenschaftsseitenklasse für das Steuerelement bereit, die von [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md) abgeleitet wird.  Erstens diese Eigenschaftenseite leer, aber Sie können ein beliebiges Dialogfeld\-Steuerelement oder Gruppe Steuerelemente hinzufügen.  Da der ActiveX\-Steuerelement\-Assistent nur eine Eigenschaftenseitenklasse standardmäßig erstellt, müssen die zusätzlichen Eigenschaftenseitenklassen \(auch abgeleitet von `COlePropertyPage`\) der Klassenansicht erstellt werden.  Weitere Informationen über diese Schritte, finden Sie unter [MFC\-ActiveX\-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).  
  
 Eine Eigenschaftenseite zu implementieren \(in diesem Fall, ist die Standardeinstellung\) ein drei Schritten statt:  
  
#### So implementieren eine Eigenschaftenseite  
  
1.  Fügen Sie `COlePropertyPage` abgeleiteten Klasse z Steuerelementprojekt hinzu.  Wenn das Projekt mithilfe des ActiveX\-Steuerelement\-Assistenten \(als in diesem Fall\) erstellt wurde, ist die Standardeigenschaftsseitenklasse bereits.  
  
2.  Verwenden Sie den Dialog\-Editor, um alle Steuerelemente der Eigenschaftenseitenvorlage hinzuzufügen.  
  
3.  Anpassen der Funktion `DoDataExchange``COlePropertyPage` abgeleiteten Klasse in den Gegenwerten zwischen dem Eigenschaftenseitensteuerelement und dem ActiveX\-Steuerelement.  
  
 Beispielsweise Zwecken, mithilfe der folgenden Verfahren ein einfaches Steuerelement \(mit "B"\).  Beispiel wurde mit dem ActiveX\-Steuerelement\-Assistenten erstellt und nur die vordefinierte Beschriftungseigenschaft enthält.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a> Hinzufügen von Steuerelementen zu einer Eigenschaftenseite  
  
#### Weitere Steuerelemente einer Eigenschaftenseite hinzufügen  
  
1.  Öffnen Sie das Steuerelementprojekt geöffnet, offene Ressourcenansicht.  
  
2.  Doppelklicken Sie auf das **Dialogfeld** Verzeichnissymbol.  
  
3.  Öffnen Sie das Dialogfeld **IDD\_PROPPAGE\_SAMPLE** .  
  
     Der ActiveX\-Steuerelement\-Assistent fügt den Namen des Projekts am Ende Dialogfeld der ID in diesem Fall Beispiel.  
  
4.  Ziehen Sie das ausgewählte Steuerelement aus der Toolbox auf den Dialogfeldbereich.  
  
5.  Für dieses Beispiel ein Beschriftungssteuer"Beschriftung: " und ein Eingabefeldsteuerelement mit einem **IDC\_CAPTION** Bezeichner sind ausreichend.  
  
6.  Klicken Sie auf der Symbolleiste auf **Speichern**, um die Änderungen zu speichern.  
  
 Nachdem die Benutzeroberfläche geändert wurde, müssen Sie das Bearbeitungsfeld mit der Beschriftungseigenschaft verknüpfen.  Dies wird im folgenden Abschnitt durchgeführt, indem die `CSamplePropPage::DoDataExchange`\-Funktion behandelt.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a> Anpassen der DoDataExchange\-Funktion  
 Die Eigenschaftenseite [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)\-Funktion ermöglicht das Linkeigenschaftenseitenwerten mit den eigentlichen Werte von Eigenschaften im Steuerelement.  Um Links erstellen, müssen Sie den entsprechenden Eigenschaftenseitenfeldern ihren jeweiligen Steuerelementeigenschaften zugeordnet sind.  
  
 Diese Zuordnungen werden mithilfe der Eigenschaftenseite **DDP\_**\-Funktionen implementiert.  Die **DDP\_**\-Funktionen funktionieren wie die **DDX\_**\-Funktionen, die in Standard\-MFC\-Dialogfeldern, mit einer Ausnahme verwendet werden.  Außer den Verweis bei einer Membervariablen, nehmen **DDP\_**\-Funktionen den Namen der Steuerelementeigenschaft.  Der Folgende ist ein typischer Eintrag in der `DoDataExchange`\-Funktion für eine Eigenschaftenseite.  
  
 [!CODE [NVC_MFC_AxUI#31](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#31)]  
  
 Diese Funktion wird die `m_caption`\-Membervariable der Eigenschaftenseite mit der Beschriftung, mit der Funktion `DDP_TEXT` zu.  
  
 Nachdem Sie das Eigenschaftenseitensteuerelement einfügen haben, müssen Sie einen Link zwischen dem Eigenschaftenseitensteuerelement, `IDC_CAPTION` und den tatsächlichen Steuerelementeigenschaft, Beschriftung, mithilfe der **DDP\_Text**\-Funktion erstellen, wie oben beschrieben.  
  
 [Eigenschaftenseiten](../mfc/reference/property-pages-mfc.md) sind für andere Dialogfeldsteuerelementtypen, wie Kontrollkästchen, Optionsfeldern und Listenfelder verfügbar.  Die folgende Tabelle zeigt den gesamten Anweisungssatz der Eigenschaftenseite **DDP\_**\-Funktionen und deren Parametern auf:  
  
### Eigenschaftenseiten\-Funktionen  
  
|Funktionsname|Verwenden Sie diese Funktion, um zu verknüpfen|  
|-------------------|----------------------------------------------------|  
|`DDP_CBIndex`|Der ausgewählten Index der Zeichenfolge in einem Kombinationsfeld mit eine Steuerelementeigenschaft.|  
|`DDP_CBString`|Die ausgewählte Zeichenfolge in einem Kombinationsfeld mit eine Steuerelementeigenschaft.  Die ausgewählte Zeichenfolge kann, mit den gleichen Buchstaben wie der Eigenschaftswert starten muss jedoch nicht, ihn vollständig übereinstimmen.|  
|`DDP_CBStringExact`|Die ausgewählte Zeichenfolge in einem Kombinationsfeld mit eine Steuerelementeigenschaft.  Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen genau übereinstimmen.|  
|`DDP_Check`|Ein Kontrollkästchen mit eine Steuerelementeigenschaft.|  
|`DDP_LBIndex`|Der ausgewählten Index der Zeichenfolge in einem Listenfeld mit eine Steuerelementeigenschaft.|  
|`DDP_LBString`|Die ausgewählte Zeichenfolge in einem Listenfeld mit eine Steuerelementeigenschaft.  Die ausgewählte Zeichenfolge kann, mit den gleichen Buchstaben wie der Eigenschaftswert starten muss jedoch nicht, ihn vollständig übereinstimmen.|  
|`DDP_LBStringExact`|Die ausgewählte Zeichenfolge in einem Listenfeld mit eine Steuerelementeigenschaft.  Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen genau übereinstimmen.|  
|`DDP_Radio`|Ein Optionsfeld mit eine Steuerelementeigenschaft.|  
|**DDP\_Text**|Text mit eine Steuerelementeigenschaft.|  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md)