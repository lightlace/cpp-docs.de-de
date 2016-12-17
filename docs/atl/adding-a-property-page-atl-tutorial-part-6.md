---
title: "Hinzuf&#252;gen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
caps.latest.revision: 15
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eigenschaftenseiten werden als separate COM\-Objekte implementiert, die nach Bedarf können freigegeben werden können.  In diesem Schritt führen Sie die folgenden Aufgaben, eine Eigenschaftenseite zum \- Steuerelement hinzuzufügen:  
  
-   Erstellen der Eigenschaftenseiten\-Ressource  
  
-   Code hinzufügen, um die Eigenschaftenseite zu erstellen und zu verwalten  
  
-   Hinzufügen der Eigenschaftenseite an das Steuerelement  
  
## Erstellen der Eigenschaftenseiten\-Ressource  
 Um eine Eigenschaftenseite dem Steuerelement hinzuzufügen, verwenden Sie den ATL\-Assistentenzum Hinzufügen von Klassen.  
  
#### So fügen Sie eine Eigenschaftenseite hinzufügen  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf, Polygon.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Ziehen Sie aus der Liste der Vorlagen, von Auswahl\- **ATL\-Eigenschaftenseite** und von auf **Hinzufügen**.  
  
4.  Wenn der ATL\-Eigenschaftenseiten\-Assistent angezeigt wird, geben Sie `PolyProp` als der **Kurz** Name ein.  
  
5.  Klicken Sie auf **Zeichenfolgen**, um die Seite zu öffnen **Zeichenfolgen** und **&Polygon** als **Titel** einzugeben.  
  
     **Titel** der Eigenschaftenseite ist die Zeichenfolge, die auf der Registerkarte für diese Seite angezeigt wird.  **Dokumentzeichenfolge** ist eine Beschreibung, die ein Eigenschaftenrahmen verwendet, um in eine Statuszeile oder QuickInfos einzufügen.  Beachten Sie, dass der Standardeigenschaftenrahmen derzeit nicht diese Zeichenfolge verwendet, sodass Sie sie mit dem Standardinhalt lassen.  Sie generieren nicht **Hilfedatei** zum Zeitpunkt, und löschen Sie den Eintrag in diesem Textfeld.  
  
6.  Klicken Sie auf **Fertig stellen** und das Eigenschaftenseitenobjekt wird erstellt.  
  
 Die folgenden drei Dateien werden erstellt:  
  
|Datei|Description|  
|-----------|-----------------|  
|PolyProp.h|Enthält die `CPolyProp` C\+\+\-Klasse, die die Eigenschaftenseite implementiert.|  
|PolyProp.cpp|Enthält die PolyProp.h\-Datei ein.|  
|PolyProp.rgs|Das Registrierungsskript, das das Eigenschaftenseitenobjekt registriert.|  
  
 Die folgenden Codeänderungen übernommen werden:  
  
-   Die neue Eigenschaftenseite wird zur Objekteintragszuordnung in Polygon.cpp hinzugefügt.  
  
-   Die `PolyProp`\-Klasse wird zur Polygon.idl\-Datei hinzugefügt.  
  
-   Die neue Registrierungsskriptdatei PolyProp.rgs wird zur Projektressource hinzugefügt.  
  
-   Eine Dialogfeldvorlage wird zur Projektressource für die Eigenschaftenseite hinzugefügt.  
  
-   Die Eigenschaftzeichenfolgen, dass Sie angegeben haben, werden dem Ressourcenzeichenfolgentabelle hinzugefügt.  
  
 Fügen Sie jetzt die Felder hinzu, die Sie auf der Eigenschaftenseite angezeigt werden sollen.  
  
#### Weitere Felder der Eigenschaftenseite hinzufügen  
  
1.  Klicken Sie im Projektmappen\-Explorer, doppelklicken Sie auf die Polygon.rc\-Ressourcendatei.  Hierdurch wird Ressourcenansicht.  
  
2.  Erweitern Sie in der Ressourcenansicht den Dialogknoten und doppelklicken Sie auf IDD\_POLYPROP.  Beachten Sie, dass das Dialogfeld, das angezeigt wird, mit Ausnahme einer Bezeichnung leer ist, die Ihnen erläutert, um die Steuerelemente hier einzufügen.  
  
3.  Wählen Sie diese Bezeichnung aus und ändern Sie sie, um `Seiten:` lesen, indem Sie den **Beschriftung** Text **Eigenschaften** im Fenster ändern.  
  
4.  Ändern Sie das Bezeichnungsfeld xxxx 1, sodass die Größe des Texts anpasst.  
  
5.  Ziehen Sie ein Bearbeitungssteuerelement aus der Toolbox auf der rechten Seite der Bezeichnung.  
  
6.  Ändern Sie abschließend **ID** des Bearbeitungssteuerelements annehmen `IDC_SIDES` mithilfe des Eigenschaftenfensters.  
  
 Dies schließt die Erstellung der Eigenschaftenseitenressource ab.  
  
## Code hinzufügen, um die Eigenschaftenseite zu erstellen und zu verwalten  
 Nachdem Sie die Eigenschaftenseitenressource erstellt haben, müssen Sie den Implementierungscode schreiben.  
  
 Zunächst können Sie die `CPolyProp`\-Klasse, um die Anzahl vonseiten im Objekt festzulegen, wenn die Schaltfläche **Übernehmen** gedrückt wird.  
  
#### Um das zugewiesen ändern arbeiten Sie die Anzahl vonseiten festzulegen  
  
1.  Ersetzen Sie die `Apply`\-Funktion in PolyProp.h durch folgenden Code:  
  
     [!CODE [NVC_ATL_Windowing#58](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#58)]  
  
 Eine Eigenschaftenseite kann mehr als einen Client, der gleichzeitig zu deren, sodass, die angefügt werden `Apply`\-Funktionsschleifen haben herum und ruft `put_Sides` auf jedem Client mit dem Wert auf, der vom Eingabefeld abgerufen wird.  Sie verwenden die [CComQIPtr](../atl/reference/ccomqiptr-class.md)\-Klasse, die `QueryInterface` auf jedem Objekt ausführt, um die `IPolyCtl`\-Schnittstelle aus der **IUnknown**\-Schnittstelle zu erhalten \(gespeichert `m_ppUnk` im Array\).  
  
 Mit dem Code Überprüfungen jetzt, ob das Festlegen der Eigenschaft `Sides` tatsächlich funktioniert.  Wenn es fehl, wird der Code ein Meldungsfeld an, das Fehlerdetails aus der **IErrorInfo**\-Schnittstelle anzeigt.  In der Regel wird ein Container eines Objekts die **ISupportErrorInfo**\-Schnittstelle und ruft `InterfaceSupportsErrorInfo` zuerst auf, bestimmen, ob das Objekt Einstellungsfehlerinformationen unterstützt.  Sie können diese Aufgabe überspringen.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) hilft Ihnen, indem automatisch die Verweiszählung behandelt, sodass es nicht erforderlich, um `Release` für die Schnittstelle aufzurufen.  `CComBSTR` können Sie mit `BSTR` Verarbeitung, deshalb müssen Sie den abschließenden `SysFreeString` Aufruf nicht ausführen.  Außerdem verwenden Sie eine der verschiedenen Zeichenkonvertierungsklassen, sodass Sie `BSTR` ggf. konvertieren \(daher ist das `USES_CONVERSION`\-Makro am Anfang der Funktion\).  
  
 Sie müssen auch das geänderte Flag der Eigenschaftenseite festlegen, um anzugeben, dass die Schaltfläche **Übernehmen** aktiviert werden soll.  Dies tritt auf, wenn der Benutzer den Wert im Eingabefeld **Seiten** ändert.  
  
#### Um die übernehmensschaltfläche behandeln  
  
1.  Klicken Sie in der Klassenansicht auf CPolyProp mit der rechten Maustaste auf und klicken Sie auf **Eigenschaften** im Kontextmenü.  
  
2.  Klicken Sie im Eigenschaftenfenster auf das Symbol **Ereignisse**.  
  
3.  Erweitern Sie die Liste `IDC_SIDES` Knotens im Ereignishandler.  
  
4.  Wählen Sie `EN_CHANGE` aus, und klicken Sie im Dropdownmenü rechts auf **\<Hinzufügen\> OnEnChangeSides**.  Die `OnEnChangeSides`\-Handlerdeklaration wird zu Polyprop.h und der Handlerimplementierung zu Polyprop.cpp hinzugefügt.  
  
 Als Nächstes ändern Sie den Handler.  
  
#### Um die OnEnChangeSides\-Methode ändern  
  
1.  Fügen Sie folgenden Code in Polyprop.cpp der `OnEnChangeSides`\-Methode hinzu \(Code aus der der Assistent dort abgelegt\):  
  
     [!CODE [NVC_ATL_Windowing#59](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#59)]  
  
 `OnEnChangeSides` wird aufgerufen, wenn eine **WM\_COMMAND** Meldung mit der **EN\_CHANGE** Benachrichtigung für das Steuerelement `IDC_SIDES` gesendet wird.  `OnEnChangeSides` ruft dann `SetDirty` auf und übergibt `TRUE`, um die Eigenschaftenseite anzugeben ist jetzt geändert und die Schaltfläche **Übernehmen** sollte aktiviert werden.  
  
## Hinzufügen der Eigenschaftenseite an das Steuerelement  
 Der ATL\-Assistentzum Hinzufügen von Klassen und der ATL\-Eigenschaftenseiten\-Assistent fügen die Eigenschaftenseite nicht dem Steuerelement automatisch hinzu, dass es mehrere Steuerelemente im Projekt geben kann.  Sie müssen einen Eintrag der Eigenschaftenzuordnung des Steuerelements hinzufügen.  
  
#### Um die Eigenschaftenseite hinzufügen  
  
1.  Öffnen Sie PolyCtl.h und fügen Sie diese Zeile der Eigenschaftenzuordnung hinzu:  
  
     [!CODE [NVC_ATL_Windowing#60](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#60)]  
  
 Die Eigenschaftenzuordnung des Steuerelements sieht nun wie folgt aus:  
  
 [!CODE [NVC_ATL_Windowing#61](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#61)]  
  
 Sie können ein Makro mit `PROP_PAGE` CLSID der Eigenschaftenseite hinzugefügt wurden, aber, wenn Sie das `PROP_ENTRY`\-Makro wie gezeigt verwenden, wird der `Sides`\-Eigenschaftswert auch gespeichert, wenn das Steuerelement gespeichert wird.  
  
 Die drei Parameter an das Makro sind die Eigenschaftenbeschreibung, den DISPID der Eigenschaft und die CLSID der Eigenschaftenseite, die die Eigenschaft dafür verfügt.  Dies ist nützlich, wenn beispielsweise laden Sie das Steuerelement in Visual Basic und die Anzahl vonseiten zur Entwurfszeit fest.  Da die Anzahl der Seiten gespeichert wird, wenn Sie das Visual Basic\-Projekt erneut laden, wird die Anzahl vonseiten wiederhergestellt.  
  
## Erstellen und Testen des Steuerelements  
 Jetzt erstellen Sie dieses Steuerelement und fügen Sie sie in Testcontainer für ActiveX\-Steuerelemente ein.  im Testcontainer auf dem Menü **Bearbeiten**, auf **PolyCtl\-Klassenobjekt**.  Die Eigenschaftenseite wird; Klicken Sie auf die Registerkarte **Polygon**.  
  
 Die Schaltfläche **Übernehmen** wird zunächst deaktiviert.  Starten Sie die Eingabe eines Werts im Feld **Seiten** und die Schaltfläche **Übernehmen** ist aktiviert.  Nachdem Sie beendet haben, den Wert anzugeben, klicken Sie auf die Schaltfläche **Übernehmen**.  Die Kontrollanzeigeänderungen und die Schaltfläche **Übernehmen** wird erneut deaktiviert.  Versuch, der einen ungültigen Wert eingibt.  Es wird ein Meldungsfeld, die Fehlerbeschreibung zu enthalten dass Sie die von der `put_Sides`\-Funktion.  
  
 Als Nächstes fügen Sie das Steuerelement auf eine Webseite.  
  
 [Zurück zu Schritt 5](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [Klicken Sie zu Schritt 7](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)