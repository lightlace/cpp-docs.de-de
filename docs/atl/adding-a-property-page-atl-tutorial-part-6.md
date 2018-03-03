---
title: "Hinzufügen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 067c5d662fee3838a33a3b53fd5dab2946ab50cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Hinzufügen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6)
Eigenschaftenseiten werden als separate COM-Objekte implementiert, die wodurch die ihnen ermöglichen, auf gemeinsam genutzt werden, falls erforderlich. Führen Sie in diesem Schritt zum Hinzufügen einer Eigenschaftenseite für das Steuerelement die folgenden Aufgaben:  
  
-   Erstellen die Eigenschaftenseitenressource  
  
-   Hinzufügen von Code zum Erstellen und verwalten die Eigenschaftsseite "  
  
-   Hinzufügen der Eigenschaftenseite für das Steuerelement  
  
## <a name="creating-the-property-page-resource"></a>Erstellen die Eigenschaftenseitenressource  
 Um das Steuerelement eine Eigenschaftenseite hinzuzufügen, verwenden Sie ATL-Assistenten zum Hinzufügen-Klasse.  
  
#### <a name="to-add-a-property-page"></a>Hinzufügen einer Eigenschaftenseite  
  
1.  Im Projektmappen-Explorer mit der rechten Maustaste Polygon.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  Wählen Sie in der Liste der Vorlagen, **ATL-Eigenschaftenseite** , und klicken Sie auf **hinzufügen**.  
  
4.  Wenn Sie die ATL-Eigenschaftenseiten-Assistent angezeigt wird, geben Sie `PolyProp` als die **kurze** Name.  
  
5.  Klicken Sie auf **Zeichenfolgen** So öffnen die **Zeichenfolgen** Seite, und geben Sie **& Polygon** als die **Titel**.  
  
     Die **Titel** der Eigenschaft Seite ist die Zeichenfolge, die auf der Registerkarte für diese Seite wird angezeigt. Die **Doc Zeichenfolge** finden Sie eine Beschreibung, die ein Frame Eigenschaft verwendet wird, in einen Status oder eine QuickInfo aufgenommen werden sollen. Beachten Sie, dass der Standardeigenschaft Frame dieser Zeichenfolge übereinstimmt, derzeit nicht verwendet, damit Sie es mit den Standardinhalt lassen können. Generieren Sie keine **Hilfedatei** im Moment so löschen Sie den Eintrag im Textfeld.  
  
6.  Klicken Sie auf **Fertig stellen**, und die Eigenschaft Page-Objekt erstellt werden.  
  
 Die folgenden drei Dateien werden erstellt:  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|PolyProp.h|Die C++-Klasse enthält `CPolyProp`, implementiert die Eigenschaftsseite ".|  
|PolyProp.cpp|Enthält die PolyProp.h-Datei an.|  
|PolyProp.rgs|Die Registrierungsskript, das die Eigenschaft Page-Objekt registriert.|  
  
 Die folgenden codeänderungen sind auch vorgenommen:  
  
-   Die neue Eigenschaftsseite wird der Eintrag objektzuordnung in Polygon.cpp hinzugefügt.  
  
-   Die `PolyProp` Klasse in der Datei Polygon.idl hinzugefügt.  
  
-   Die neue Registrierungsskriptdatei PolyProp.rgs wird auf die Projektressource hinzugefügt.  
  
-   Die Projektressource für die Eigenschaftenseite wird eine Dialogfeldvorlage hinzugefügt.  
  
-   Die Eigenschaftenzeichenfolgen, die Sie angegeben werden die Ressourcen-Zeichenfolgentabelle hinzugefügt.  
  
 Fügen Sie nun die Felder, die auf der Eigenschaftenseite angezeigt werden sollen.  
  
#### <a name="to-add-fields-to-the-property-page"></a>Um Felder hinzuzufügen, um die Eigenschaftsseite "  
  
1.  Doppelklicken Sie im Projektmappen-Explorer auf die Ressourcendatei Polygon.rc. Dadurch wird die Ressourcenansicht geöffnet.  
  
2.  Klicken Sie in der Ressourcenansicht erweitern Sie den Dialogfeld-Knoten, und doppelklicken Sie auf IDD_POLYPROP. Beachten Sie, dass das Dialogfeld leer mit Ausnahme einer Bezeichnung, die Sie So fügen Sie hier Ihre Steuerelemente informiert.  
  
3.  Wählen Sie diese Bezeichnung, und ändern sie die Zeichenfolge `Sides:` durch Ändern der **Beschriftung** Text in der **Eigenschaften** Fenster.  
  
4.  Ändern Sie die Größe des Bezeichnungsfelds, damit sie die Größe des Texts passen.  
  
5.  Ziehen Sie ein Bearbeitungssteuerelement aus der Toolbox in die rechts neben der Beschriftung.  
  
6.  Abschließend ändern Sie die **ID** des Bearbeitungssteuerelements zum `IDC_SIDES` mithilfe des Eigenschaftenfensters.  
  
 Dies schließt die Eigenschaftenseitenressource erstellen.  
  
## <a name="adding-code-to-create-and-manage-the-property-page"></a>Hinzufügen von Code zum Erstellen und verwalten die Eigenschaftsseite "  
 Nun, dass Sie die Eigenschaftenseitenressource erstellt haben, müssen Sie den Implementierungscode schreiben.  
  
 Aktivieren Sie zunächst die `CPolyProp` Klasse, um die Anzahl der Seiten in das Objekt bei der **übernehmen** gedrückt wird.  
  
#### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>So ändern Sie die Funktion anwenden, um die Anzahl der Seiten festzulegen  
  
1.  Ersetzen Sie die `Apply` in PolyProp.h-Funktion mit den folgenden Code:  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 Eine Eigenschaftenseite kann mehr als einen Client zu einem Zeitpunkt angefügt haben also die `Apply` Funktion führt eine Schleife ein und ruft `put_Sides` auf jedem Client mit dem Wert, der vom im Bearbeitungsfeld abgerufen. Verwenden Sie die [CComQIPtr](../atl/reference/ccomqiptr-class.md) -Klasse, die führt der `QueryInterface` für jedes Objekt zum Abrufen der `IPolyCtl` -Schnittstelle aus der **IUnknown** Schnittstelle (in gespeicherten der `m_ppUnk` Array).  
  
 Der Code überprüft nun, dass durch Festlegen der `Sides` -Eigenschaft funktioniert hat. Falls dies fehlschlägt, wird der Code zeigt ein Meldungsfeld mit Fehlerdetails aus der **IErrorInfo** Schnittstelle. In der Regel fragt ein Container ein Objekt für die **ISupportErrorInfo** -Schnittstelle und ruft `InterfaceSupportsErrorInfo` ersten, um festzustellen, ob das Objekt den Fehler Einstellungsinformationen unterstützt. Sie können diese Aufgabe überspringen.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) hilft Ihnen durch die automatisch Behandlung der verweiszählung, daher Sie nicht aufrufen müssen `Release` auf der Schnittstelle. `CComBSTR`hilft Ihnen mit `BSTR` verarbeiten, müssen Sie nicht zum Ausführen der endgültige `SysFreeString` aufrufen. Außerdem verwenden Sie eine der die verschiedenen Klassen für die zeichenfolgenkonvertierung, damit konvertiert werden kann die `BSTR` bei Bedarf (deswegen der `USES_CONVERSION` -Makro ist zu Beginn der Funktion).  
  
 Sie müssen auch die Eigenschaftenseite modifizierte Flag gibt an, dass Festlegen der **übernehmen** Schaltfläche aktiviert werden soll. Dies tritt auf, wenn der Benutzer den Wert in ändert die **Seiten** Eingabefeld.  
  
#### <a name="to-handle-the-apply-button"></a>Behandeln Sie die Schaltfläche "anwenden"  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste CPolyProp, und klicken Sie auf **Eigenschaften** im Kontextmenü.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Symbol.  
  
3.  Erweitern Sie die `IDC_SIDES` Knoten in der Ereignisliste.  
  
4.  Wählen Sie `EN_CHANGE`, und klicken Sie auf das Dropdownmenü rechts auf  **\<hinzufügen > OnEnChangeSides**. Die `OnEnChangeSides` Handlerdeklaration wird Polyprop.h und die Handlerimplementierung PolyProp.cpp hinzugefügt werden.  
  
 Als Nächstes ändern Sie den Handler.  
  
#### <a name="to-modify-the-onenchangesides-method"></a>So ändern Sie die OnEnChangeSides-Methode  
  
1.  Fügen Sie den folgenden Code in Polyprop.cpp auf die `OnEnChangeSides` Methode (jeglicher Code, der vom Assistenten gelöscht):  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides`wird aufgerufen, wenn eine **WM_COMMAND** Nachricht wird gesendet, mit der **EN_CHANGE** Benachrichtigung für den `IDC_SIDES` Steuerelement. `OnEnChangeSides`Ruft dann `SetDirty` und übergibt `TRUE` an, dass die Eigenschaft nun Seite fehlerhaft ist und die **übernehmen** Schaltfläche aktiviert werden soll.  
  
## <a name="adding-the-property-page-to-the-control"></a>Hinzufügen der Eigenschaftenseite für das Steuerelement  
 ATL-Assistent zum Hinzufügen-Klasse und die ATL-Eigenschaftenseiten-Assistent fügen die Eigenschaftsseite "an das Steuerelement für Sie automatisch und Sie keine da es möglicherweise mehrere Steuerelemente, die in Ihrem Projekt. Sie müssen einen Eintrag zur Eigenschaft-steuerelementzuordnung hinzufügen.  
  
#### <a name="to-add-the-property-page"></a>So fügen Sie die Eigenschaftenseite hinzu  
  
1.  Öffnen Sie PolyCtl.h hinzu, und fügen Sie diese Zeile auf die eigenschaftszuordnung:  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 Das Steuerelement eigenschaftenzuordnung sieht nun wie folgt:  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 Sie konnte hinzugefügt haben, eine `PROP_PAGE` Makro mit der CLSID der Eigenschaftenseite, wenn Sie jedoch die `PROP_ENTRY` Makro wie gezeigt, die `Sides` Eigenschaftswert wird auch gespeichert, wenn das Steuerelement gespeichert wird.  
  
 Die drei Parameter für das Makro gibt die Beschreibung der Eigenschaft, die die DISPID der Eigenschaft und die CLSID der Eigenschaftenseite, die die Eigenschaft enthält. Dies ist hilfreich, wenn Sie z. B. laden das Steuerelement in Visual Basic und die Anzahl der Seiten zur Entwurfszeit festgelegt. Da die Anzahl der Seiten gespeichert wird, wenn Sie das Visual Basic-Projekt erneut laden, wird die Anzahl der Seiten wiederhergestellt werden.  
  
## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements  
 Nun erstellen Sie das entsprechende Steuerelement und Testcontainer für ActiveX-Steuerelement einfügen. Im Test-Container auf die **bearbeiten** Menü klicken Sie auf **PolyCtl-Klassenobjekt**. Die Eigenschaftenseite angezeigt wird; Klicken Sie auf die **Polygon** Registerkarte.  
  
 Die **übernehmen** Schaltfläche anfänglich deaktiviert ist. Geben Sie einen Wert in der **Seiten** Feld und die **übernehmen** Schaltfläche aktiviert wird. Nachdem Sie die Eingabe des Werts abgeschlossen haben, klicken Sie auf die **übernehmen** Schaltfläche. Die Anzeige Steuerelement geändert wird, und die **übernehmen** Schaltfläche erneut deaktiviert ist. Versuchen Sie einen ungültigen Wert einzugeben. Sehen Sie ein Meldungsfeld, enthält die fehlerbeschreibung, die Sie festlegen, aus der `put_Sides` Funktion.  
  
 Sie werden als nächstes Steuerelement auf einer Webseite einfügen.  
  
 [Zurück zu Schritt 5](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [Mit Schritt 7 fort](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)

