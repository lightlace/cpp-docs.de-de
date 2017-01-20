---
title: "TN022: Implementieren von Standardbefehlen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.commands"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehle, Standard"
  - "ID_APP_ABOUT-Befehl"
  - "ID_APP_EXIT-Befehl"
  - "ID_CONTEXT_HELP-Befehl"
  - "ID_DEFAULT_HELP-Befehl"
  - "ID_EDIT_CLEAR-Befehl"
  - "ID_EDIT_CLEAR_ALL-Befehl"
  - "ID_EDIT_COPY-Befehl"
  - "ID_EDIT_CUT-Befehl"
  - "ID_EDIT_FIND-Befehl"
  - "ID_EDIT_PASTE-Befehl"
  - "ID_EDIT_PASTE_LINK-Befehl"
  - "ID_EDIT_PASTE_SPECIAL-Befehl"
  - "ID_EDIT_REDO-Befehl"
  - "ID_EDIT_REPEAT-Befehl"
  - "ID_EDIT_REPLACE-Befehl"
  - "ID_EDIT_SELECT_ALL-Befehl"
  - "ID_EDIT_UNDO-Befehl"
  - "ID_FILE_CLOSE-Befehl"
  - "ID_FILE_NEW-Befehl"
  - "ID_FILE_OPEN-Befehl"
  - "ID_FILE_PAGE_SETUP-Befehl"
  - "ID_FILE_PRINT-Befehl"
  - "ID_FILE_PRINT_PREVIEW-Befehl"
  - "ID_FILE_PRINT_SETUP-Befehl"
  - "ID_FILE_SAVE-Befehl"
  - "ID_FILE_SAVE_AS-Befehl"
  - "ID_FILE_SAVE_COPY_AS-Befehl"
  - "ID_FILE_UPDATE-Befehl"
  - "ID_HELP-Befehl"
  - "ID_HELP_INDEX-Befehl"
  - "ID_HELP_USING-Befehl"
  - "ID_INDICATOR_CAPS-Befehl"
  - "ID_INDICATOR_EXT-Befehl"
  - "ID_INDICATOR_KANA-Befehl"
  - "ID_INDICATOR_NUM-Befehl"
  - "ID_INDICATOR_OVR-Befehl"
  - "ID_INDICATOR_REC-Befehl"
  - "ID_INDICATOR_SCRL-Befehl"
  - "ID_NEXT_PANE-Befehl"
  - "ID_OLE_EDIT_LINKS-Befehl"
  - "ID_OLE_INSERT_NEW-Befehl"
  - "ID_OLE_VERB_FIRST-Befehl"
  - "ID_PREV_PANE-Befehl"
  - "ID_VIEW_STATUS_BAR-Befehl"
  - "ID_VIEW_TOOLBAR-Befehl"
  - "ID_WINDOW_ARRANGE-Befehl"
  - "ID_WINDOW_CASCADE-Befehl"
  - "ID_WINDOW_NEW-Befehl"
  - "ID_WINDOW_SPLIT-Befehl"
  - "ID_WINDOW_TILE_HORZ-Befehl"
  - "ID_WINDOW_TILE_VERT-Befehl"
  - "Standardbefehle"
  - "TN022"
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# TN022: Implementieren von Standardbefehlen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Standardbefehlsimplementierungen, die von MFC 2.0 bereitgestellt werden.  Lesen Sie zuerst [Technischer Hinweis 21](../mfc/tn021-command-and-message-routing.md), da es die Mechanismen beschrieben, die verwendet werden, um viele der Standardbefehle zu implementieren.  
  
 Diese Beschreibung akzeptiert Kenntnisse der MFC\-Architekturen, der APIs und des allgemeinen Programmierstils an.  Dokumentierte sowie nicht dokumentierten "Implementierung" nur APIs werden beschrieben.  Dies ist kein Platz, um den Erfahrens über die Funktionen von oder, wie in MFC.  Siehe Visual C\+\+ mit allgemeinerer Informationen und Details von dokumentierten APIs.  
  
## Das Problem  
 MFC definiert viele Standardbefehls\-IDs in der Headerdatei AFXRES.H.  Frameworkunterstützung für diese Befehle variieren.  Das Verständnis, wo und wie die .NET\-Framework\-Klassen behandeln, diese Befehle Ihnen nicht nur anzeigen, wie das Framework intern jedoch, funktioniert, nützliche Informationen bereitstellen wird auf, wie die Standardimplementierungen Anpassen und Ihnen verschiedene Techniken zum Implementieren eigener Befehlshandler lernen.  
  
## Inhalt des Hinweises technischen  
 Jede Befehls\-ID wird in zwei Abschnitten beschrieben:  
  
-   Der Titel: der symbolische Name der Befehls\-ID, \(beispielsweise **ID\_FILE\_SAVE**\) gefolgt vom Zweck des Befehls, \(z "Speicher das aktuelle Dokument"\) getrennt durch einen Doppelpunkt.  
  
-   Eine oder mehrere Absätze, die beschreiben, welche Klassen den Befehl implementieren und die Standardimplementierung wird  
  
 Die meisten Standardbefehlsimplementierungen sind in der Basisklassenmeldungszuordnung des Frameworks prewired.  Es gibt mehrere Befehlsimplementierungen, die explizite die Verknüpfung in der abgeleiteten Klasse erforderlich.  Diese werden unter "Note" beschrieben.  Wenn die Optionen im Anwendungs\-Assistenten rechten ausgewählt haben, werden diese Standardhandler für Sie im generierten Anwendungsskelett verbunden.  
  
## Namenskonvention  
 Standardbefehle folgen einer einfachen Namenskonvention, dass wir Sie Verwendung wird empfohlen, falls möglich.  Die meisten Standardbefehle sind in den Standardplätzen in der Menüleiste einer Anwendung.  Der symbolischer Name der Befehlsanfänge mit "ID\_" gefolgt vom Standardpopupmenünamen, gefolgt vom Menüelementnamen.  Der symbolischer Name ist im Unterstrichwortbrüchen mit Großbuchstaben.  Bei Befehlen, die Standard nicht haben, benennt Menüelement, ein logischer Befehlsname entspricht definiertes Starten mit "ID\_", \(beispielsweise **ID\_NEXT\_PANE**\).  
  
 Wir verwenden das Präfix "ID\_", um Befehle anzugeben, die entwickelt wurden, auf die Menüelemente, den Schaltflächen oder anderen Befehlsbenutzeroberflächeobjekte gebunden werden.  Die Befehlshandler, die "ID\_\-" Befehle behandeln, sollten `ON_COMMAND` verwenden und `ON_UPDATE_COMMAND_UI` Mechanismen des MFC anweisen Architektur.  
  
 Sie sollten Sie verwenden das Präfix des Standardanbieters "IDM\_" für Menüelemente, die nicht der Befehlsarchitektur folgen und Menübesonderecode erfordern, um sie zu aktivieren und zu deaktivieren.  Natürlich macht die Zahl des Menüs, das bestimmte Befehle, seit dem nach der MFC\-Befehlsarchitektur, klein sein sollen nicht nur, leistungsfähiger Befehlshandler \(da sie mit Symbolleisten arbeiten\), jedoch wird den Befehlshandlercode wiederverwendbar.  
  
## ID Bereiche  
 finden Sie unter [Technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) für weitere Details bei der Verwendung von ID\-Bereichen in MFC an.  
  
 MFC\-Standardbefehle fallen in den Bereich 0xE000 auf 0xEFFF.  Bitte erstellen Sie nicht auf die spezifischen Werte dieser IDs, da sie ändern in zukünftigen Versionen der Bibliothek sind.  
  
 Ihre Anwendung muss seine Befehle im Bereich 0x8000 zu 0xDFFF definieren.  
  
## Standardbefehls\-IDs  
 Für jede Befehls\-ID gibt es eine Standardmeldungszeileneingabeaufforderungs\-zeichenfolge, die in der Datei PROMPTS.RC gefunden werden kann.  Die Zeichenfolgen\-ID für diese Menüeingabeaufforderung muss dieselbe wie für die ID Befehl sein  
  
-   ID\_FILE\_NEW erstellt, ein neues Dokument\/leert.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnFileNew` implementiert diesen Befehl als je nach Anzahl von Dokumentvorlagen in der Anwendung.  Wenn nur ein `CDocTemplate` gibt, wird `CWinApp::OnFileNew` ein neues Dokument dieses Typs und die richtigen Frame und die Ansichtsklasse.  
  
     Wenn mehrere `CDocTemplate` gibt, wird `CWinApp::OnFileNew` dem ein Dialogfeld \(**AFX\_IDD\_NEWTYPEDLG**\) wählen sie werden auf, die zu verwenden der Dokumenttyp.  Die ausgewählte `CDocTemplate` wird verwendet, um das Dokument zu erstellen.  
  
     Eine typische Anpassung von `ID_FILE_NEW` ist, und eine andere grafischere Auswahl von Dokumenttypen bereitzustellen.  In diesem Fall können Sie eigenes **CMyApp::OnFileNew** implementieren und in der Meldungszuordnung anstelle `CWinApp::OnFileNew` platzieren.  Es ist nicht erforderlich, die Basisklassenimplementierung aufrufen.  
  
     Eine weitere allgemeine Anpassung von `ID_FILE_NEW`, einen separaten Befehl für das Erstellen eines Dokuments jedes Typs bereitstellen.  In diesem Fall sollten Sie neue Befehls\-IDs, beispielsweise ID\_FILE\_NEW\_CHART und ID\_FILE\_NEW\_SHEET definieren.  
  
-   ID\_FILE\_OPEN wird ein vorhandenes Dokument.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnFileOpen` verfügt über eine sehr einfache Implementierung das Aufrufen von **CWinApp::DoPromptFileName** gefolgt von `CWinApp::OpenDocumentFile` mit der Datei oder den Pfadnamen der Datei, um diese zu öffnen.  Die `CWinApp` Implementierung Routine\- **DoPromptFileName** bewegt das oben Standard\-FileOpen\-Dialogfeld und füllt ihn mit den Dateierweiterungen aus, die den aktuellen von Dokumentvorlagen abgerufen werden.  
  
     Eine typische Anpassung von `ID_FILE_OPEN` ist, das FileOpen\-Dialogfeld anzupassen oder zusätzliche Dateifilter hinzuzufügen.  Die empfohlene Methode, dieses ist, anzupassen die Standardimplementierung von ein eigenes FileOpen\-Dialogfeld und Aufruf `CWinApp::OpenDocumentFile` mit der Belegdatei oder den Pfadnamen zu ersetzen.  Es ist nicht erforderlich, die Basisklasse aufzurufen.  
  
-   ID\_FILE\_CLOSE schließt das aktuell geöffnete Dokument.  
  
     **CDocument::OnFileClose** ruft `CDocument::SaveModified` auf, um den Benutzer aufzufordern, das Dokument zu speichern, wenn sie geändert wurde und ruft dann `OnCloseDocument` auf.  Die gesamte Logik schließt, einschließlich das Zerstören des Dokuments, ist in der Routine `OnCloseDocument` ausgeführt.  
  
    > [!NOTE]
    >  **ID\_FILE\_CLOSE** sich unterschiedlich einer `WM_CLOSE` Meldung oder einem **SC\_CLOSE** Systembefehl dass z Dokumentrahmenfenster.  Das Verbinden eines Fensters schließt das Dokument nur, wenn das letzte Rahmenfenster ist, das das Dokument angezeigt.  Durch Schließen des Dokuments mit **ID\_FILE\_CLOSE** nicht nur das Dokument schließt, aber enthält alle unten Rahmenfenster, die das Dokument anzeigen.  
  
-   ID\_FILE\_SAVE sichert das aktuelle Dokument.  
  
     Die Implementierung verwendet eine Hilfe Routine\-, die **CDocument::DoSave** für **OnFileSave** und **OnFileSaveAs** verwendet wird.  Wenn Sie ein Dokument, das nicht gespeichert wurde vor \(das heißt, es, haben einen Pfadnamen, wie nicht im Ereignishandler FileNew\) speichern, oder dem von einem schreibgeschützten Dokument gelesen wurde, die **OnFileSave** Logik wie der Befehl **ID\_FILE\_SAVE\_AS** verhält und den Benutzer auffordert, einen neuen Dateinamen anzugeben.  Der eigentliche Bestimmung des Öffnens der Datei und des Höhe der Speichern wurde durch die virtuelle `OnSaveDocument`\- Funktion ausgeführt.  
  
     Es gibt zwei gängige, Gründe **ID\_FILE\_SAVE** anzupassen.  Weitere Dokumente, die erst speichern, entfernen Sie einfach die **ID\_FILE\_SAVE** Menüelemente und \-Symbolleistenschaltflächen der Benutzeroberfläche.  Stellen Sie außerdem, ob rufen Sie nie geändert das Dokument \(d, nie `CDocument::SetModifiedFlag`\) und das Framework wird nie das Dokument gespeichert.  Für Dateien, die auf auf eine andere Stelle als einer Datenträgerdatei speichern, definieren Sie einen neuen Befehl für diesen Vorgang.  
  
     Bei `COleServerDoc` wird **ID\_FILE\_SAVE** für Dateiabwehr \(für normale Dokumente\) und Dateiupdate verwendet \(für eingebettete Dokumente\).  
  
     Wenn die Dokumentdaten in einzelnen Datenträgerdateien gespeichert werden, jedoch nicht das standardmäßige **CDocument** verwenden möchten serialisieren Implementierung, sollte `CDocument::OnSaveDocument` anstelle von **OnFileSave** überschreiben.  
  
-   ID\_FILE\_SAVE\_AS sichert das aktuelle Dokument unter einem anderen Dateinamen.  
  
     **CDocument::OnFileSaveAs** Die Implementierung verwendet dieselbe **CDocument::DoSave** Hilfsfunktion wie **OnFileSave**.  Der Befehl **OnFileSaveAs** wird nur als **ID\_FILE\_SAVE** behandelt, wenn die Dokumente keinen Dateinamen vor der Abwehr hätten.  **COleServerDoc::OnFileSaveAs** implementiert die Logik, um eine normale Dokumentdatendatei zu speichern oder ein Serverdokument speichern, das ein OLE\-Objekt darstellt, der in einer anderen Anwendung als separate Datei eingebettet wird.  
  
     Wenn Sie die Logik von **ID\_FILE\_SAVE** anpassen, möchten Sie wahrscheinlich **ID\_FILE\_SAVE\_AS** oder den Vorgang "speichern in ähnliche Weise anpassen, z" nicht auf das Dokument angewendet werden kann.  Sie können das Menüelement der Menüleiste entfernen, die nicht benötigt wird.  
  
-   ID\_FILE\_SAVE\_COPY\_AS Speichern einer Kopie aktuelle Dokument unter einem neuen Namen.  
  
     Die **COleServerDoc::OnFileSaveCopyAs** Implementierung entspricht **CDocument::OnFileSaveAs** sehr ähnlich, außer dass das Dokumentobjekt ist nicht auf die zugrunde liegende Datei nach der Abwehr "angefügt."  Das bedeutet, dass, wenn das Dokument im Arbeitsspeicher "verändert" wurde, bevor den Speicherungs\-, noch "geändert wird".  Darüber hinaus verfügt dieser Befehl keine Auswirkungen auf den Pfadnamen oder den Titel, die im Dokument gespeichert sind.  
  
-   ID\_FILE\_UPDATE benachrichtigt den Container, ein eingebettetes Dokument speichern.  
  
     Die Implementierung `COleServerDoc::OnUpdateDocument` einfach notifiies der Container, dass die Einbettung gespeichert werden soll.  Der Container ruft dann die entsprechenden OLE\-APIs auf, um das eingebettete Objekt zu speichern.  
  
-   ID\_FILE\_PAGE\_SETUP ruft eine anwendungsspezifische Seiteneinrichtung\/ein Layoutdialogfeld auf.  
  
     Derzeit es gibt keinen Standardwert für dieses Dialogfeld, und das Framework hat keine Standardimplementierung dieses Befehls.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_FILE\_PRINT\_SETUP\-Aufruf das Standarddrucks\-Setupdialogfeld.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     Dieser Befehl wird das Standarddrucksetupdialogfeld auf, das dem Benutzer ermöglicht, um den Drucker und die Druckeinstellungen für dieses Dokument oder höchstens alle Dokumente in dieser Anwendung mindestens anzupassen.  Sie müssen die Systemsteuerung verwenden, um die Standarddruckereinstellungen für das gesamte System zu ändern.  
  
     `CWinApp::OnFilePrintSetup` verfügt über eine sehr einfache Implementierung, die ein `CPrintDialog`\-Objekt erstellt und die **CWinApp::DoPrintDialog** Implementierungsfunktion aufruft.  Legt das Anwendungsstandard\-Druckersetup fest.  
  
     Die allgemeine Anforderung zum Anpassen dieses Befehls ist, ProDokumentdruckereinstellungen zuzulassen, die mit dem Dokument gespeichert werden, wenn sie gespeichert werden.  Um dies zu erreichen, das Sie einen Meldungszuordnungshandler in der **CDocument**\-Klasse hinzufügen sollten die ein `CPrintDialog`\-Objekt erstellt, mit den entsprechenden Druckerattributen \(normalerweise **hDevMode** und **hDevNames**\) initialisiert, rufen Sie **CPrintDialog::DoModal,** und speichern Sie die geänderte Druckereinstellungen.  Eine stabilen Implementierung sollten Sie die Implementierung von **CWinApp::DoPrintDialog** betrachten nach dem Erkennen von Fehlern und **CWinApp::UpdatePrinterSelection** nach dem mit vernünftige Standards und das Verfolgen von Druckeränderungen systemweiten.  
  
-   ID\_FILE\_PRINT\-Standarddruck des aktuellen Dokuments  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CView` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     Dieser Befehl ausgibt das aktuelle Dokument oder ordnungsgemäß, bei der der Druckvorgang, einschließt, das Standarddruckdialogfeld und Ausführen das Aufrufen Druckmodul.  
  
     **CView::OnFilePrint** implementiert diesen Befehl und die Hauptdruckschleife.  Sie ruft virtuelle `CView::OnPreparePrinting` an der Eingabeaufforderung des Benutzers mit dem Druckdialogfeld auf.  Es können dann die, Domänencontroller auszugeben, um den Drucker zu wechseln, wird nach dem Druckstatusdialogfeld \(**AFX\_IDD\_PRINTDLG**\) und sendet das `StartDoc` Escapezeichen den Drucker.  **CView::OnFilePrint** enthält auch die Seite\-ausgerichtete Main Druckschleife.  Für jede Seite ruft die virtuelle `CView::OnPrepareDC` gefolgt von einem `StartPage` Escapezeichen und vom Aufrufen virtuellen `CView::OnPrint` für diese Seite auf.  Wenn vollständig virtuelle, wird `CView::OnEndPrinting` aufgerufen, und das Druckstatusdialogfeld wird geschlossen.  
  
     Die MFC\-Druckarchitektur wurde entwickelt, um auf viele verschiedene Arten für das Drucken und Druckvorschau einzubinden.  Sie suchen normalerweise die verschiedenen Funktionen überschreibbaren `CView`, die für alle Seite\-ausgerichteten druckenden Aufgaben angemessen sind.  Nur im Fall einer Anwendung, das verwendet, richtete der Drucker für NichtSeite Ausgabe aus, wenn die Anforderung suchen, die **ID\_FILE\_PRINT** Implementierung zu ersetzen.  
  
-   ID\_FILE\_PRINT\_PREVIEW\-EINGABETASTE\-Seitenansichtsmodus für das aktuelle Dokument.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CView` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     **CView::OnFilePrintPreview** startet den Seitenansicht, indem die dokumentierte Hilfsfunktion **CView::DoPrintPreview** aufruft.  **CView::DoPrintPreview** ist Hauptmodul in für die Seitenansichtsschleife, wie **OnFilePrint** Hauptmodul in für die Druckschleife ist.  
  
     Der Seitenansichtsvorgang kann auf verschiedene Art angepasst werden, indem verschiedene Parameter an **DoPrintPreview** übergibt.  Einzelheiten erfahren Sie im [Technischer Hinweis 30](../mfc/tn030-customizing-printing-and-print-preview.md) an, das einige Details der Druckvorschau erläutert und wie sie angepasst wird.  
  
-   Bereich **ID\_FILE\_MRU\_FILE1**...**FILE16**  Eine von Befehls\-IDs für die Datei MRU `list`.  
  
     **CWinApp::OnUpdateRecentFileMenu** ist ein Updatebefehlsbenutzeroberflächenhandler, der einer der erweiterte Verwendungen des `ON_UPDATE_COMMAND_UI` Mechanismus ist.  In Ihrer Menüressource müssen Sie lediglich ein einzelnes Menüelement mit ID **ID\_FILE\_MRU\_FILE1** definieren.  Dieses Menüelement zuerst bleibt, deaktiviert.  
  
     Während die MRU\-Liste zunimmt, werden weitere Menüelemente der Liste hinzugefügt.  Die Standard\- `CWinApp` Implementierung führt zu dem Standardlimit vier der zuletzt verwendeten Dateien.  Sie können die Standardeinstellung ändern, indem Sie `CWinApp::LoadStdProfileSettings` mit einem größeren oder kleineren Wert aufrufen.  Die MRU\-Liste wird in der INI\-Datei der Anwendung gespeichert.  Die Liste ist in `InitInstance`\-Funktion der Anwendung geladen, wenn Sie `LoadStdProfileSettings` aufrufen, und gespeichert, wenn die Anwendung beendet.  Der MRU\-Updatebefehlsbenutzeroberflächenhandler auch konvertiert absolute Pfade zu den relativen Pfaden für die Anzeige auf dem Dateimenü.  
  
     **CWinApp::OnOpenRecentFile** ist der `ON_COMMAND`\-Handler, der den eigentlichen Befehl ausführt.  Sie ruft einfach den Dateinamen aus der MRU\-Liste ab und ruft `CWinApp::OpenDocumentFile` auf, die die gesamte Arbeit das Öffnen der Datei und Aktualisieren der MRU\-Liste ausgegeben.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_EDIT\_CLEAR löscht die aktuelle Auswahl  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls mit `CEdit::Clear`.  Der Befehl wird deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_CLEAR\_ALL löscht das gesamte Dokument.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  Siehe die Implementierung MFC\-Referenten\- Beispiel\- [SCRIBBLE](../top/visual-cpp-samples.md) als Beispiel.  
  
-   ID\_EDIT\_COPY kopiert die aktuelle Auswahl in die Zwischenablage.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der den derzeit markierten Text in die Zwischenablage als CF\_TEXT mit `CEdit::Copy` kopiert.  Der Befehl wird deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_CUT schneidet die aktuelle Auswahl zur Zwischenablage aus.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der den derzeit markierten Text in die Zwischenablage als CF\_TEXT mit `CEdit::Cut` ausgeschnitten wird.  Der Befehl wird deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_FIND beginnt den Suchvorgang, nimmt oben das nicht modale Dialogfeld "Suche".  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der die Implementierungshilfsfunktion **OnEditFindReplace** aufruft, um zu verwenden und die vorherige Suche zu speichern\/Einstellungen in privaten Implementierungsvariablen ersetzen Sie.  Die `CFindReplaceDialog`\-Klasse wird verwendet, um das nicht modale Dialogfeld für die Eingabeaufforderung des Benutzers zu verwalten.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_PASTE fügt den aktuellen Inhalt der Zwischenablage ein.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der die aktuelle Zwischenablage kopiert, die den ausgewählten Text mithilfe von `CEdit::Paste` ersetzen.  Der Befehl wird deaktiviert, wenn kein **CF\_TEXT** in der Zwischenablage sind.  
  
     **COleClientDoc** stellt nur einen Updatebefehlsbenutzeroberflächenhandler für diesen Befehl bereit.  Wenn die Zwischenablage kein integrierbares OLE\-Element\/ein Objekt enthält, wird der Befehl deaktiviert.  Sie sind für das Schreiben des Handlers verantwortlich, sodass der tatsächliche Befehl das tatsächliche Einfügen durchführt.  Wenn die OLE\-Anwendung andere Stile auch einfügen kann, sollten Sie einen eigenen Updatebefehlsbenutzeroberflächenhandler in der Ansicht oder in Dokument bereitstellen, also bevor die **COleClientDoc** im Befehlszielrouting\).  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
     Für das Ersetzen der Implementierung des standardmäßigen OLE, verwenden Sie `COleClientItem::CanPaste`.  
  
-   ID\_EDIT\_PASTE\_LINK fügt einen Link vom aktuellen Inhalt der Zwischenablage ein.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `COleDocument` umfasst derzeit einen Updatebefehlsbenutzeroberflächenhandler für diesen Befehl bereit.  Wenn die Zwischenablage nicht verbindbares OLE\-Element\/Objekt enthält, wird der Befehl deaktiviert.  Sie sind für das Schreiben des Handlers verantwortlich, sodass der tatsächliche Befehl das tatsächliche Einfügen durchführt.  Wenn die OLE\-Anwendung andere Stile auch einfügen kann, sollten Sie einen eigenen Updatebefehlsbenutzeroberflächenhandler in der Ansicht oder in Dokument bereitstellen, also bevor die `COleDocument` im Befehlszielrouting\).  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
     Für das Ersetzen der Implementierung des standardmäßigen OLE, verwenden Sie `COleClientItem::CanPasteLink`.  
  
-   ID\_EDIT\_PASTE\_SPECIAL fügt den aktuellen Inhalt der Zwischenablage mit Optionen ein.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  MFC stellt nicht das Dialogfeld.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_REPEAT wiederholt die letzten Vorgang.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, den letzten Suchvorgang zu überprüfen.  Die privaten Implementierungsvariablen für die letzten Suche verwendet werden.  Der Befehl wird deaktiviert, wenn eine Suche nicht versucht werden kann.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_REPLACE startet den Ersetzungsvorgang, nimmt oben das nicht modale Dialogfeld. Ersetzen  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der die Implementierungshilfsfunktion **OnEditFindReplace** aufruft, um zu verwenden und die vorherige Suche zu speichern\/Einstellungen in privaten Implementierungsvariablen ersetzen Sie.  Die `CFindReplaceDialog`\-Klasse wird verwendet, um das nicht modale Dialogfeld zu verwalten, das den Benutzer auffordert.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_SELECT\_ALL wählt das gesamte Dokument.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, der den gesamten Text im Dokument auswählt.  Der Befehl wird deaktiviert, wenn kein Text auszuwählen, gibt.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_UNDO macht den letzten Vorgang rückgängig.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     `CEditView` stellt eine Implementierung dieses Befehls, mit `CEdit::Undo`.  Der Befehl wird deaktiviert, wenn `CEdit::CanUndo` FALSE zurückgibt.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_EDIT\_REDO wiederholt die letzten Vorgang.  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für jedes von `CView` abgeleitete Klasse implementieren.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_WINDOW\_NEW öffnet ein anderes Fenster im aktiven Dokument.  
  
     **CMDIFrameWnd::OnWindowNew** implementiert diese leistungsstarke Funktion, indem die Normal\-Vorlage des aktuellen Dokuments verwendet, um eine andere Frames zu erstellen, die eine andere Ansicht des aktuellen Dokuments enthalten.  
  
     Wie die meisten Multiple Document Interface \(MDI\)\- Fenstermenübefehle wird der Befehl deaktiviert, wenn kein aktives untergeordnetes MDI\-Fenster gibt.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  Wenn Sie einen Befehl bereitstellen möchten, der weitere Ansichten oder Rahmenfenster, sind Sie wahrscheinlich besser, einen eigenen erfinden Befehl.  Sie können den Code von **CMDIFrameWnd::OnWindowNew** klonen und ihn bestimmten Frame und der Ansichtsklassen des Mögens ändern.  
  
-   ID\_WINDOW\_ARRANGE ordnet Symbole am unteren Rand ein MDI\-Fenster an.  
  
     `CMDIFrameWnd` implementiert diesen Befehl standardmäßigen MDI in einer Implementierungshilfsfunktion **OnMDIWindowCmd**.  Diese Hilfe ordnet Befehls\-IDs zu MDI\-Windows\-Meldungen zu und kann deshalb vielem Code freigeben.  
  
     Wie die meisten MDI\-Fenstermenübefehle wird der Befehl deaktiviert, wenn kein aktives untergeordnetes MDI\-Fenster gibt.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_WINDOW\_CASCADE kaskadiert Fenster, sodass schneiden sie.  
  
     `CMDIFrameWnd` implementiert diesen Befehl standardmäßigen MDI in einer Implementierungshilfsfunktion **OnMDIWindowCmd**.  Diese Hilfe ordnet Befehls\-IDs zu MDI\-Windows\-Meldungen zu und kann deshalb vielem Code freigeben.  
  
     Wie die meisten MDI\-Fenstermenübefehle wird der Befehl deaktiviert, wenn kein aktives untergeordnetes MDI\-Fenster gibt.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_WINDOW\_TILE\_HORZ\-Kachelfenster horizontal.  
  
     Dieser Befehl wird in `CMDIFrameWnd` wie **ID\_WINDOW\_CASCADE** implementiert, außer eine andere MDI\-Windows\-Meldung für den Vorgang verwendet wird.  
  
     Sie sollten die Standardkachelausrichtung für die Anwendung wählen.  Sie erreichen dies, indem Sie die ID für das Fenster\-" Kachel" Menüelement entweder von **ID\_WINDOW\_TILE\_HORZ** oder **ID\_WINDOW\_TILE\_VERT** ändern.  
  
-   ID\_WINDOW\_TILE\_VERT\-Kachelfenster vertikal.  
  
     Dieser Befehl wird in `CMDIFrameWnd` wie **ID\_WINDOW\_CASCADE** implementiert, außer eine andere MDI\-Windows\-Meldung für den Vorgang verwendet wird.  
  
     Sie sollten die Standardkachelausrichtung für die Anwendung wählen.  Sie erreichen dies, indem Sie die ID für das Fenster\-" Kachel" Menüelement entweder von **ID\_WINDOW\_TILE\_HORZ** oder **ID\_WINDOW\_TILE\_VERT** ändern.  
  
-   ID\_WINDOW\_SPLIT\-Tastaturschnittstelle den Splitter.  
  
     `CView` behandelt diesen Befehl für die Implementierung. `CSplitterWnd` Wenn die Ansicht ein Teil eines Splitterfensters ist, delegiert dieser Befehl zur Implementierungsfunktion `CSplitterWnd::DoKeyboardSplit`.  Dies fügt den Splitter in einem Modus wird, der zu geteiltem oder zu ungeteiltem ein Splitterfenster zulässig.  
  
     Dieser Befehl wird deaktiviert, wenn die Ansicht nicht in einen Splitter ist.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_APP\_ABOUT ruft das Dialogfeld Info auf.  
  
     Es gibt keine standardmäßige Implementierung für eine Anwendung über Feld.  Die standardmäßige Anwendungs\-Assistent\-erstellte Anwendung erstellt eine benutzerdefinierte Dialogfeldklasse für die Anwendung und verwendet sie als das ungefähr Feld.  Anwendungs\-Assistent Außerdem schreibt trivialen den Befehlshandler, der den Befehl verarbeitet und das Dialogfeld aufgerufen wird.  
  
     Sie implementieren fast immer über diesen Befehl.  
  
-   ID\_APP\_EXIT\-Beendigung die Anwendung.  
  
     **CWinApp::OnAppExit** behandelt diesen Befehl, indem eine `WM_CLOSE` Meldung im Hauptfenster der Anwendung sendet.  Das Standardabschalten der Anwendung \(Eingabeaufforderung für geänderte Dateien usw.\) wird durch die Implementierung `CFrameWnd` behandelt.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  Durch Überschreiben von `CWinApp::SaveAllModified` oder von Logik von `CFrameWnd` verwenden.  
  
     Wenn Sie festlegen, um diesen Befehl zu implementieren, wird empfohlen Sie verwenden diesen Befehl ID  
  
-   ID\_HELP\_INDEX führt Hilfethemen von .HLP\-Datei auf.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnHelpIndex` behandelt diesen Befehl, indem belanglos `CWinApp::WinHelp` aufruft.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_HELP\_USING\-Anzeigen helfen auf, wie die Hilfe verwendet.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnHelpUsing` behandelt diesen Befehl, indem belanglos `CWinApp::WinHelp` aufruft.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_CONTEXT\_HELP gibt Modus der Hilfe SHIFT\-F1 ein.  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnContextHelp` behandelt diesen Befehl, indem der Hilfemodus\-Cursor festlegt, einer modalen Schleife eingibt und auf den Benutzer, um ein Fenster auszuwählen, um die Hilfe an abzurufen wartet.  finden Sie unter [Technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für weitere Informationen auf der MFC\-Hilfeimplementierung an.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_HELP gibt Hilfe zum aktuellen Kontext  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     `CWinApp::OnHelp` behandelt diesen Befehl, indem der rechten Hilfekontext für den aktuellen Anwendungskontext abruft.  Dieses einfache behandelt F1\-Hilfe, Hilfe in Meldungsfeldern B.  finden Sie unter [Technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für weitere Informationen auf der MFC\-Hilfeimplementierung an.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_DEFAULT\_HELP\-Anzeigen nehmen Hilfe für Kontext den Standardwert an  
  
    > [!NOTE]
    >  Sie müssen dieses an das `CWinApp` herstellen \- die Meldungszuordnung der abgeleiteten Klasse, um diese Funktionalität zu aktivieren.  
  
     Dieser Befehl wird normalerweise `CWinApp::OnHelpIndex` zugeordnet.  
  
     Ein weiterer Befehlshandler kann bereitgestellt werden, wenn eine Unterscheidung zwischen standardmäßigen und Hilfe im Hilfeindex gewünscht wird.  
  
-   ID\_NEXT\_PANE wechselt zum nächsten Bereich  
  
     `CView` behandelt diesen Befehl für die Implementierung. `CSplitterWnd` Wenn die Ansicht ein Teil eines Splitterfensters ist, delegiert dieser Befehl zur Implementierungsfunktion **CSplitterWnd::OnNextPaneCmd**.  Dies wird die aktive Ansicht auf den folgenden Bereich im Splitter.  
  
     Dieser Befehl wird deaktiviert, wenn die Ansicht nicht in einen Splitter ist, oder es keinen folgenden Bereich gibt, zu wechseln.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_PREV\_PANE wechselt zum vorherigen Splitterfenster  
  
     `CView` behandelt diesen Befehl für die Implementierung. `CSplitterWnd` Wenn die Ansicht ein Teil eines Splitterfensters ist, delegiert dieser Befehl zur Implementierungsfunktion **CSplitterWnd::OnNextPaneCmd**.  Dies wird die aktive Ansicht auf den vorherigen Bereich im Splitter.  
  
     Dieser Befehl wird deaktiviert, wenn die Ansicht nicht in einen Splitter ist, oder es keinen vorherigen Bereich gibt, zu wechseln.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_OLE\_INSERT\_NEW fügt ein neues OLE\-Objekt ein  
  
     Derzeit gibt es keine Standardimplementierung für diesen Befehl.  Sie müssen dieses für das `CView` abgeleitete Klasse implementieren, um ein neues OLE\-Elements\/des Objekts bei der aktuellen Auswahl einzufügen.  
  
     Alle OLE\-Clientanwendungen sollten diesen Befehl implementieren.  Anwendungs\-Assistent, mit der OLE\-Option, erstellt ein Implementierungsskelett von **OnInsertObject** in der Ansichtsklasse, die Sie ausführen müssen.  
  
     Siehe das Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE Beispielfür eine vollständige Implementierung dieses Befehls.  
  
-   ID\_OLE\_EDIT\_LINKS bearbeitet OLE\-Links  
  
     `COleDocument` behandelt diesen Befehl, indem sie verwendet, MFC\-zurVerfügung bereitgestellten Implementierung des Linkdialogfelds standardmäßigen OLE.  Auf die Implementierung dieses Dialogfelds wird durch die `COleLinksDialog`\-Klasse zugegriffen.  Wenn das aktuelle Dokument keine Links enthält, wird der Befehl deaktiviert.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   ID\_OLE\_VERB\_FIRST... LETZT ein ID\-Bereich für OLE\-Verben  
  
     `COleDocument` verwendet diesen Befehls\-ID\-Bereich für die Verben, die vom aktuell ausgewählte OLE\-Element\/das Objekt unterstützt werden.  Dies muss ein Bereich sich, da ein angegebenes OLE\-Element\/ein Objekttyp keine oder mehrere benutzerdefinierte Verben unterstützen können.  Im Menü der Anwendung sollten Sie ein Menüelement mit ID von **ID\_OLE\_VERB\_FIRST** verfügen.  Wenn das Programm ausgeführt wird, wird das Menü mit der entsprechenden Menüverbbeschreibung aktualisiert \(oder Popupmenü mit vielen Verben\).  Die Verwaltung des OLE\-Menüs wird von `AfxOleSetEditMenu` behandelt, ausgeführt im Updatebefehlsbenutzeroberflächenhandler für diesen Befehl.  
  
     Es gibt keine expliziten Befehlshandler zum Behandeln jede der Befehls\-ID in diesem Bereich.  **COleDocument::OnCmdMsg** wird überschrieben, um alle Befehls\-IDs in diesem Bereich aufzufangen, sie zu Verbzahlen nullbasierte auszuführen, und Server für dieses Verb zu starten \(mit `COleClientItem::DoVerb`\).  
  
     Anpassung oder anderer Verwendung dieses Befehls\-ID\-Bereich wird nicht empfohlen.  
  
-   ID\_VIEW\_TOOLBAR aktiviert die Symbolleiste zu aktivieren bzw. um  
  
     `CFrameWnd` behandelt diese Befehl und die UpdateBefehl Benutzeroberflächenhandler, sichtbaren den Zustand der Symbolleiste zu wechseln.  Die Symbolleiste muss ein untergeordnetes Fenster des Frames mit ID des untergeordneten Fensters von `AFX_IDW_TOOLBAR` sein.  Der Befehlshandler schaltet tatsächlich die Sichtbarkeit des Symbolleistenfensters um.  `CFrameWnd::RecalcLayout` wird verwendet, um das Rahmenfenster mit der Symbolleiste in ihrem neuen Zustand neu zu zeichnen.  Der UpdateBefehl Benutzeroberflächenhandler überprüft das Menüelement, wenn die Symbolleiste sichtbar ist.  
  
     Anpassung dieses Befehlshandlers wird nicht empfohlen.  Wenn Sie zusätzliche Symbolleisten hinzufügen möchten, möchten Sie den Befehlshandler und den UpdateBefehl Benutzeroberflächenhandler für diesen Befehl klonen und ändern.  
  
-   ID\_VIEW\_STATUS\_BAR aktiviert die Statusleiste an und deaktiviert um  
  
     Dieser Befehl wird in `CFrameWnd` wie **ID\_VIEW\_TOOLBAR** implementiert, außer eine andere ID des untergeordneten Fensters \(**AFX\_IDW\_STATUS\_BAR**\) verwendet wird.  
  
## Nur zur Aktualisierung Befehlshandler  
 Einige Standardbefehls\-IDs werden Indikatoren als in den Statusleisten verwendet.  Diese verwenden denselben UpdateBefehl Benutzeroberflächen\-Behandlungsmechanismus, um den aktuellen visuellen Zustand während der Anwendungsleerlaufzeit anzuzeigen.  Da sie nicht vom Benutzer \(das heißt, Sie können einen Statusleistenbereich nicht drücken\), ausgewählt werden können, ist es überflüssig, einen Handler `ON_COMMAND` für diese Befehls\-IDs verfügen.  
  
-   **ID\_INDICATOR\_CAPS** : GROSSBUCHSTABENsperrenindikator.  
  
-   **ID\_INDICATOR\_NUM** : Indikator der NUMERISCHEN Sperre.  
  
-   **ID\_INDICATOR\_SCRL** : ROLLEN\-Sperrenindikator.  
  
-   **ID\_INDICATOR\_KANA** : KANA\-Sperrenindikator \(gilt nur den japanischen Systemen\).  
  
 Alle drei dieser werden in **CFrameWnd::OnUpdateKeyIndicator**, einer Implementierungshilfe implementiert, die die Befehls\-ID verwendet, um zur entsprechenden virtuellen Schlüssel zugeordnet werden soll.  Eine allgemeine Implementierung ermöglicht oder deaktiviert \(für die Statusbereiche deaktiviert \= kein Text\) das `CCmdUI`\-Objekt abhängig, ob die richtige virtuelle Taste nur gesperrt ist.  
  
 Anpassung dieses Befehlshandlers wird nicht empfohlen.  
  
-   **ID\_INDICATOR\_EXT : EXT** beendet ausgewählten Indikator.  
  
-   Streikindikator **ID\_INDICATOR\_OVR : OV** e **R**.  
  
-   **ID\_INDICATOR\_REC : MAK**, das ording Indikator ist.  
  
 Derzeit gibt es keine Standardimplementierung für die Indikatoren.  
  
 Wenn Sie festlegen, um diese Indikatoren zu implementieren, wird empfohlen Sie verwenden diese Zähler IDs und die Wartung der Reihenfolge der Indikatoren in der Statusleiste \(das heißt, in dieser Reihenfolge: EXT, CAPITAL, NUM, ROLLEN, ÜB, REC\).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)