---
title: 'Tn022: Implementieren von Standard-Befehle Implementierung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.commands
dev_langs:
- C++
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dea42f4bd33281e65696791677bdd81a921a59e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385524"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Implementieren von Standardbefehlen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem Hinweis werden die Standardbefehls-Implementierungen von MFC 2.0 bereitgestellt werden. Lesen [technischen Hinweis 21](../mfc/tn021-command-and-message-routing.md) zuerst, da die Mechanismen zum Großteil der Standardbefehle implementieren beschrieben.  
  
 Diese Beschreibung setzt Kenntnisse der MFC-Architekturen, APIs und allgemeine programmiergrundlagen. Dokumentierte als auch nicht dokumentierte "Implementierung nur" APIs beschrieben werden. Dies ist kein Ausgangspunkt über die Funktionen der oder die Programmierung in MFC zu erfahren. Weitere allgemeine Informationen und ausführliche dokumentierten APIs, finden Sie in Visual C++.  
  
## <a name="the-problem"></a>Das Problem  
 MFC definiert viele Standardbefehls-IDs in der Headerdatei AFXRES. H. Framework-Unterstützung für diese Befehle variiert. Verstehen, wo und wie die Framework-Klassen mit diesen Befehlen behandeln erfahren nicht nur Sie, wie das Framework intern funktioniert, aber bietet nützliche Informationen zum Anpassen der standardimplementierungen und erfahren Sie einige Techniken zum Implementieren von eigene Befehlshandler.  
  
## <a name="contents-of-this-technical-note"></a>Inhalt dieser technischen Hinweis  
 Jedes Befehls-ID wird in zwei Abschnitten beschrieben:  
  
-   Der Titel: symbolischen Namens des Befehls-ID (z. B. **ID_FILE_SAVE**) gefolgt von den Zweck des Befehls (z. B. "speichert das aktuelle Dokument") durch einen Doppelpunkt getrennt sind.  
  
-   Eine oder mehrere Absätze, beschreibt die Klassen implementieren, mit dem Befehl, und was bewirkt, dass die standardmäßige Implementierung  
  
 Die meisten standardimplementierungen Befehl werden in das Framework Basisklasse meldungszuordnung prewired. Es gibt einige Befehl-Implementierungen, die explizite Verkabelung in die abgeleitete Klasse zu erfordern. Diese werden unter "Hinweis" beschrieben. Wenn Sie die richtigen Optionen in AppWizard ausgewählt haben, werden diese Standardhandler für Sie in der generierten skelettanwendung verbunden.  
  
## <a name="naming-convention"></a>Namenskonvention  
 Standardbefehle führen Sie eine einfache Benennungskonvention, die wir empfehlen, dass Sie nach Möglichkeit verwenden. Die meisten Standardbefehle befinden sich im standardmäßigen stellen in der Menüleiste der Anwendung. Die symbolische Namen des Befehls beginnt mit "ID_" gefolgt vom Namen standard-Popup-Menü, gefolgt vom Namen Menüelements. Die symbolische Namen ist in Großbuchstaben mit Unterstrich Worttrennung. Für Befehle, die nicht mit Standardmenü Elementnamen verfügen, ist eine logische Befehlsname definiert, beginnend mit "ID_" (z. B. **ID_NEXT_PANE**).  
  
 Wir verwenden das Präfix "ID_", um Befehle anzugeben, die entwickelt wurden, um die Menüelemente, Symbolleisten-Schaltflächen oder anderen Benutzeroberflächenobjekten Befehl gebunden werden. Behandeln von Kommentaren "ID_" Befehlshandler die zu verwendende der `ON_COMMAND` und `ON_UPDATE_COMMAND_UI` Mechanismen der MFC-befehlsarchitektur.  
  
 Es wird empfohlen, dass Sie das Standardpräfix "IDM_" für Menüelemente verwenden, die nicht der-befehlsarchitektur folgen und benötigen Menü-spezifischen Code zum Aktivieren und deaktivieren sie. Natürlich sollte die Anzahl der Befehle im Menü niedrig sein, da der MFC-befehlsarchitektur folgen nicht nur Befehlshandler (da sie mit der Symbolleisten funktionieren) leistungsfähiger macht jedoch den Befehl Handlercode wiederverwendet werden stellt.  
  
## <a name="id-ranges"></a>ID-Bereiche  
 Finden Sie unter [technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) detaillierte Informationen für die Verwendung von MFC-ID-Bereiche.  
  
 MFC-Standardbefehle liegen im Bereich 0xE000 auf 0xEFFF. Bitte verlassen Sie sich nicht auf die speziellen Werte von diese IDs sie unterliegt in zukünftigen Versionen der Bibliothek enthalten sind.  
  
 Ihre Anwendung sollte die Befehle im Bereich 0 x 8000 bis 0xDFFF definieren.  
  
## <a name="standard-command-ids"></a>Standardbefehle-IDs  
 Für jedes Befehls-ID befindet sich eine Standardnachricht Zeile Prompt Zeichenfolge, die in der Datei EINGABEAUFFORDERUNGEN gefunden werden kann. RC. Die Zeichenfolgen-ID für diese Aufforderung Menü muss die gleichen wie für die Befehls-ID.  
  
-   ID_FILE_NEW wird ein neues/leeres Dokument erstellt.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnFileNew` mit diesem Befehl anders entsprechend der Anzahl von Dokumentvorlagen implementiert in der Anwendung. Wenn es Gib nur ein `CDocTemplate`, `CWinApp::OnFileNew` erstellt ein neues Dokument dieses Typs als auch die richtigen Frame und Ansicht-Klasse.  
  
     Wenn es mehr als eine `CDocTemplate`, `CWinApp::OnFileNew` fordert den Benutzer ein Dialogfeld (**AFX_IDD_NEWTYPEDLG**) birgt dies der richtige Dokumenttyp verwenden ausgewählt. Das ausgewählte `CDocTemplate` wird verwendet, um das Dokument zu erstellen.  
  
     Eine allgemeine Anpassung von `ID_FILE_NEW` besteht darin, eine andere und mehr grafische Auswahl Dokumenttypen bereitzustellen. In diesem Fall können implementieren Sie Ihr eigenes **CMyApp::OnFileNew** und fügen Sie ihn in der meldungszuordnung anstelle von `CWinApp::OnFileNew`. Es ist nicht erforderlich, die Implementierung der Basisklasse aufrufen.  
  
     Eine andere nehmen häufig die Anpassung der `ID_FILE_NEW` besteht darin, einen separaten Befehl zum Erstellen eines Dokuments der einzelnen Typen bereitzustellen. In diesem Fall sollten Sie die neuen Befehls-IDs, z. B. ID_FILE_NEW_CHART und ID_FILE_NEW_SHEET definieren.  
  
-   ID_FILE_OPEN öffnet ein vorhandenes Dokument.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnFileOpen` verfügt über eine sehr einfache Implementierung eines Aufrufs **CWinApp::DoPromptFileName** gefolgt von `CWinApp::OpenDocumentFile` mit dem Namen Datei oder Pfad der Datei zu öffnen. Die `CWinApp` Implementierung Routine **DoPromptFileName** wird das standardmäßige FileOpen-Dialogfeld geöffnet und füllt sie mit den Dateierweiterungen von der aktuellen Dokumentvorlagen abgerufen.  
  
     Eine allgemeine Anpassung von `ID_FILE_OPEN` besteht darin, das Dialogfeld "FileOpen" anpassen oder zusätzliche Filter hinzufügen. Die empfohlene Methode zum Anpassen dieser ist, ersetzen Sie die standardmäßige Implementierung mit Ihren eigenen FileOpen-Dialogfeld, und rufen `CWinApp::OpenDocumentFile` mit dem Namen des Dokuments Datei oder Pfad. Es ist nicht erforderlich, der Basisklasse aufgerufen.  
  
-   ID_FILE_CLOSE schließt das geöffnete Dokument.  
  
     **CDocument::OnFileClose** Aufrufe `CDocument::SaveModified` , die der Benutzer aufgefordert, das Dokument zu speichern, wenn er geändert wurde, und dann ruft `OnCloseDocument`. Alle schließende Logik, zerstören das Dokument, einschließlich erfolgt in der `OnCloseDocument` Routine.  
  
    > [!NOTE]
    >  **ID_FILE_CLOSE** verhält sich anders aus einem `WM_CLOSE` Nachricht oder eine **SC_CLOSE** Systembefehl an das Rahmenfenster Dokumente gesendet. Schließen eines Fensters wird das Dokument geschlossen werden, nur wenn dieser letzten Rahmenfenster zeigt das Dokument ist. Schließen des Dokuments mit **ID_FILE_CLOSE** nicht nur das Dokument geschlossen wird, aber alle Rahmenfenster zeigt das Dokument beendet wird.  
  
-   ID_FILE_SAVE speichert das aktuelle Dokument.  
  
     Die Implementierung verwendet eine Hilfsfunktion **CDocument::DoSave** für beide dient **OnFileSave** und **OnFileSaveAs**. Wenn Sie ein Dokument speichern, die noch nicht gespeichert wurde (d. h. es keinen Pfadnamen ein, wie im Fall von FileNew) oder das gelesene aus einem Dokument schreibgeschützt sind und die **OnFileSave** Logik verhält Sie sich wie die **ID_FILE_SAVE_AS** Befehl, und bitten Sie den Benutzer auf einen neuen Dateinamen anzugeben. Der tatsächliche Prozess, der die Datei öffnen und auf diese Weise speichern erfolgt über die virtuelle Funktion `OnSaveDocument`.  
  
     Es gibt zwei häufige Gründe für eine Anpassung **ID_FILE_SAVE**. Für Dokumente, die nicht speichern, entfernen Sie einfach die **ID_FILE_SAVE** Menüelemente und Symbolleisten-Schaltflächen, über die Benutzeroberfläche. Stellen Sie außerdem sicher, dass Sie niemals Ihr Dokument modifizierte Seiten (d. h. niemals Aufrufen `CDocument::SetModifiedFlag`) und das Framework wird niemals dazu führen, dass das Dokument gespeichert werden. Definieren Sie für Dokumente, die als eine Datenträgerdatei an einem beliebigen Ort zu speichern einen neuen Befehl für diesen Vorgang.  
  
     Im Fall von einem `COleServerDoc`, **ID_FILE_SAVE** wird verwendet, für die Datei speichern (für normale Dokumente) und Aktualisierung der Standortsteuerungsdatei (für eingebettete Dokumente).  
  
     Wenn die Dokumentdaten ist in einzelne Dateien gespeichert, aber nicht die Standardeinstellung verwenden möchten **CDocument** Implementierung zu serialisieren, sollten Sie überschreiben `CDocument::OnSaveDocument` anstelle von **OnFileSave**.  
  
-   ID_FILE_SAVE_AS speichert das aktuelle Dokument unter einem anderen Dateinamen an.  
  
     Die **CDocument::OnFileSaveAs** Implementierung verwendet die gleiche **CDocument::DoSave** Hilfsroutine als **OnFileSave**. Die **OnFileSaveAs** Befehl erfolgt wie **ID_FILE_SAVE** wäre die Dokumente kein Dateiname vor dem Speichern. **COleServerDoc::OnFileSaveAs** implementiert die Logik, um eine normale Dokuments-Datendatei zu speichern oder Speichern von Serverdokument ein OLE-Objekt darstellt, die in einer anderen Anwendung als separate Datei eingebettet.  
  
     Wenn Sie die Logik der anpassen **ID_FILE_SAVE**, Sie möchten wahrscheinlich anpassen **ID_FILE_SAVE_AS** in ähnlicher Weise wie bei oder die Ausführung von "Speichern unter" kann in Ihr Dokument nicht gültig. Sie können dem Menüelement, das über die Menüleiste entfernen, wenn es nicht erforderlich ist.  
  
-   ID_FILE_SAVE_COPY_AS speichert eine Kopie für die aktuelle Dokument unter einem neuen Namen.  
  
     Die **COleServerDoc::OnFileSaveCopyAs** Implementierung ähnelt **CDocument::OnFileSaveAs**, außer dass das Document-Objekt nicht "an die zugrunde liegende Datei nach dem Speichern angefügt ist". D. h., wenn das Dokument im Arbeitsspeicher "vor dem Speichern geändert wurde", ist es immer noch "modified". Darüber hinaus wirkt sich dieser Befehl nicht auf den Pfadnamen oder den Titel in das Dokument gespeichert.  
  
-   ID_FILE_UPDATE benachrichtigt den Container aus, um ein eingebettetes Dokument zu speichern.  
  
     Die `COleServerDoc::OnUpdateDocument` Implementierung einfach Notifiies der Container, der das Einbetten gespeichert werden soll. Der Container ruft dann die entsprechende OLE-APIs zum Speichern des eingebetteten Objekts.  
  
-   ID_FILE_PAGE_SETUP Ruft eine anwendungsspezifische Seite Setup/Layout-Dialogfeld.  
  
     Es gibt derzeit keinen Standard für diesen Dialog, und das Framework verfügt über keine Standardimplementierung dieses Befehls.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_FILE_PRINT_SETUP rufen die Standarddialog drucken-Setup.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     Dieser Befehl ruft die standard-drucken-Setupdialogfeld, das ermöglicht es dem Benutzer zum Anpassen des Druckers, und Drucken Einstellungen für mindestens dieses Dokuments oder höchstens alle Dokumente in dieser Anwendung. Sie müssen die Systemsteuerung verwenden, um die standarddruckereinstellungen für das gesamte System ändern.  
  
     `CWinApp::OnFilePrintSetup` verfügt über eine sehr einfache Implementierung erstellen eine `CPrintDialog` Objekt und der Aufruf der **CWinApp::DoPrintDialog** Implementierung-Funktion. Dadurch wird das Standard-Drucker Anwendungssetup festgelegt.  
  
     Die allgemeine Notwendigkeit zum Anpassen von mit diesem Befehl werden für pro-Dokument Druckereinstellungen, zuzulassen, die mit dem Dokument beim Speichern gespeichert werden sollen. Zu diesem Zweck sollten Sie eine meldungszuordnung Ereignishandler in Hinzufügen Ihrer **CDocument** -Klasse, die erstellt eine `CPrintDialog` Objekt, mit der entsprechenden Drucker Attribute initialisiert (normalerweise **hDevMode-Feld** und **hDevNames**), rufen Sie die **CPrintDialog::DoModal,** und speichern Sie die geänderten Druckereinstellungen fest. Für eine stabile Implementierung Hauptprotokoll Sie die Implementierung der **CWinApp::DoPrintDialog** zum Erkennen von Fehlern und **CWinApp::UpdatePrinterSelection** für den Umgang mit sensibler Standardwerte und Nachverfolgen von Änderungen für eine systemweite Drucker.  
  
-   ID_FILE_PRINT Standard Drucken des aktuellen Dokuments  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CView`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     Mit diesem Befehl wird das aktuelle Dokument gedruckt oder mehr richtig startet den Druckvorgang, der auch das standardmäßige Dialogfeld "Drucken" aufrufen und das Drucken-Modul ausgeführt.  
  
     **CView::OnFilePrint** implementiert, mit diesem Befehl und die Hauptschleife drucken. Ruft den virtuellen `CView::OnPreparePrinting` auf Aufforderung des Benutzers mit dem Dialogfeld "Drucken". Anschließend bereitet die Ausgabe-DC an den Drucker zu wechseln, wird das Statusdialogfeld in drucken (**AFX_IDD_PRINTDLG**), und sendet die `StartDoc` Escape an den Drucker. **CView::OnFilePrint** enthält auch die wichtigsten seitenbasierten drucken-Schleife. Für jede Seite ruft den virtuellen `CView::OnPrepareDC` gefolgt von einem `StartPage` Escape und das Aufrufen der virtuellen `CView::OnPrint` für diese Seite. Nach dem Abschluss, virtuellen `CView::OnEndPrinting` aufgerufen wird, und das Drucken Statusdialogfeld geschlossen ist.  
  
     Die MFC-drucken-Architektur soll auf viele verschiedene Arten für Drucken und Druckvorschau zu verknüpfen. Normalerweise finden Sie die verschiedenen `CView` überschreibbare-Funktionen für alle seitenbasierten Druckaufgaben ausreichend. Nur bei einer Anwendung, den Drucker verwendet für nicht-Seite Ausgabe dienstorientierten sollten Sie die Notwendigkeit, ersetzen Sie finden, die **ID_FILE_PRINT** Implementierung.  
  
-   Geben Sie ID_FILE_PRINT_PREVIEW-Seitenansichtsmodus für das aktuelle Dokument.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CView`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     **CView::OnFilePrintPreview** startet die Seitenansicht durch Aufrufen der dokumentierten Hilfsfunktion **CView::DoPrintPreview**. **CView::DoPrintPreview** ist das Haupt-Modul für die Schleife Seitenansicht ebenso **OnFilePrint** ist das Haupt-Modul für die Drucken-Schleife.  
  
     Die Seitenansicht-Vorgang kann in einer Vielzahl von Möglichkeiten angepasst werden, durch andere Parameter zu übergeben **DoPrintPreview**. Finden Sie unter [technischen Hinweis 30](../mfc/tn030-customizing-printing-and-print-preview.md), einige Details der Seitenansicht erläutert, und wie Sie es anpassen.  
  
-   **ID_FILE_MRU_FILE1**... **FILE16** einen Bereich von Befehls-IDs für die Datei MRU `list`.  
  
     **CWinApp::OnUpdateRecentFileMenu** ist ein Update UI Befehlshandler, die eine erweiterte Verwendungen ist die `ON_UPDATE_COMMAND_UI` Mechanismus. In der Menüressource definieren, müssen Sie nur ein einzelnes Menüelement mit der ID **ID_FILE_MRU_FILE1**. Das Menüelement bleibt zunächst deaktiviert.  
  
     Als die zuletzt verwendeten Objekte wächst, weitere Menü, die Elemente der Liste hinzugefügt werden. Der Standard `CWinApp` Implementierung wird standardmäßig auf standard maximal vier zuletzt verwendeten Dateien. Sie können die Standardeinstellung ändern, durch den Aufruf `CWinApp::LoadStdProfileSettings` mit einem Wert größer oder kleiner. Die MRU-Liste wird in der Anwendungsverzeichnis gespeichert. INI-Datei. Die Liste ist in der Anwendungsverzeichnis geladen `InitInstance` funktioniert, wenn Sie aufrufen `LoadStdProfileSettings`, und wird gespeichert, wenn die Anwendung beendet wird. MRU-Update UI Befehlshandler wandelt auch absolute Pfade in relative Pfade für die Anzeige auf das Dateimenü.  
  
     **CWinApp::OnOpenRecentFile** ist die `ON_COMMAND` Handler, der den tatsächlichen Befehl ausführt. Ruft einfach den Dateinamen aus der Liste zuletzt verwendeter Dateien und Aufrufe `CWinApp::OpenDocumentFile`, führt die gesamte Arbeit Öffnen der Datei, und aktualisieren die Liste der zuletzt verwendeten Objekte.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_EDIT_CLEAR löscht die aktuelle Auswahl  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung der Verwendung dieses Befehls `CEdit::Clear`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_CLEAR_ALL löscht das gesamte Dokument.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird. Finden Sie im Lernprogramm für MFC-Beispiel [SCRIBBLE](../visual-cpp-samples.md) eine Beispiel-Implementierung.  
  
-   ID_EDIT_COPY kopiert die aktuelle Auswahl in die Zwischenablage.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der den derzeitig markierten Text als HIERSVR mit in die Zwischenablage kopiert `CEdit::Copy`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_CUT schneidet die aktuelle Auswahl in die Zwischenablage.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der den derzeitig markierten Text in die Zwischenablage, wie die Verwendung von HIERSVR schneidet `CEdit::Cut`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_FIND beginnt der Suchvorgang nicht modalen wird das Suchdialogfeld geöffnet.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der die Implementierung Hilfsfunktion ruft **OnEditFindReplace** verwenden und die vorherigen Suchen/Ersetzen-Einstellungen in private implementierungsvariablen speichern. Die `CFindReplaceDialog` Klasse dient zum Verwalten der nicht modalen Dialogfeld für den Benutzer aufzufordern.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_PASTE fügt den aktuellen Inhalt der Zwischenablage ein.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der aktuellen Daten aus der Zwischenablage und Ersetzen Sie dabei mit den ausgewählten Text kopiert `CEdit::Paste`. Der Befehl ist deaktiviert, wenn keine **HIERSVR** in die Zwischenablage.  
  
     **COleClientDoc** bietet nur einen Update-Befehlshandler Benutzeroberfläche für diesen Befehl. Wenn die Zwischenablage nicht eingebettet werden OLE-Element/Objekt enthält, wird der Befehl deaktiviert. Sie sind verantwortlich für das Schreiben des Handlers für den tatsächlichen-Befehl das eigentliche einfügen möchten. Wenn die OLE-Anwendung auch andere Formate einfügen kann, sollten Sie Ihre eigenen Update-Befehlshandler UI in Ihrer Ansicht oder des Dokuments bereitstellen (d. h. an einer beliebigen Stelle vor dem **COleClientDoc** in das Ziel Befehlsrouting).  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
     Verwenden Sie zum Ersetzen der standard OLE-automatisierungsimplementierung, `COleClientItem::CanPaste`.  
  
-   ID_EDIT_PASTE_LINK Fügt einen Link aus dem aktuellen Inhalt der Zwischenablage ein.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `COleDocument` mit diesem Befehl bereit nur einen Update-Befehlshandler Benutzeroberfläche. Wenn die Zwischenablage nicht verknüpfbares OLE-Element/Objekt enthält, wird der Befehl deaktiviert. Sie sind verantwortlich für das Schreiben des Handlers für den tatsächlichen-Befehl das eigentliche einfügen möchten. Wenn die OLE-Anwendung auch andere Formate einfügen kann, sollten Sie Ihre eigenen Update-Befehlshandler UI in Ihrer Ansicht oder des Dokuments bereitstellen (d. h. an einer beliebigen Stelle vor dem `COleDocument` in das Ziel Befehlsrouting).  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
     Verwenden Sie zum Ersetzen der standard OLE-automatisierungsimplementierung, `COleClientItem::CanPasteLink`.  
  
-   ID_EDIT_PASTE_SPECIAL fügt den aktuellen Inhalt der Zwischenablage mit Optionen ein.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse. MFC bietet keine diesen Dialog.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_REPEAT wiederholt den letzten Vorgang.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung dieses Befehls in der letzten Suchvorgang wiederholen. Die private implementierungsvariablen für die letzten suchen dienen. Der Befehl ist deaktiviert, wenn eine Suche kann nicht durchgeführt werden.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_REPLACE startet der Ersetzungsvorgang nicht modalen ersetzen wird das Dialogfeld geöffnet.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der die Implementierung Hilfsfunktion ruft **OnEditFindReplace** verwenden und die vorherigen Suchen/Ersetzen-Einstellungen in private implementierungsvariablen speichern. Die `CFindReplaceDialog` Klasse dient zum Verwalten von nicht modalen Dialogfeld, die der Benutzer aufgefordert wird.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_SELECT_ALL wählt das gesamte Dokument.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung von diesem Befehl, der gesamten Text im Dokument ausgewählt. Der Befehl ist deaktiviert, wenn es kein Text ist auswählen.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_UNDO macht den letzten Vorgang rückgängig.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     `CEditView` Stellt eine Implementierung dieses Befehls mit `CEdit::Undo`. Der Befehl ist deaktiviert, wenn `CEdit::CanUndo` gibt "false" zurück.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_EDIT_REDO wiederholt den letzten Vorgang.  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für die einzelnen implementieren `CView`-Klasse.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_WINDOW_NEW wird ein weiteres Fenster für das aktive Dokument geöffnet.  
  
     **CMDIFrameWnd::OnWindowNew** implementiert dieses leistungsfähige Feature mithilfe der Dokumentvorlage des aktuellen Dokuments einen anderen Frame mit einer anderen Ansicht des aktuellen Dokuments erstellen.  
  
     Wie die meisten mehrere Document Interface (MDI) Fenster Menübefehlen ist der Befehl deaktiviert, wenn keine aktives untergeordnete MDI-Fenster vorhanden ist.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen. Falls gewünscht, einen Befehl anzugeben, der zusätzliche Ansichten oder Rahmenfenster erstellt wird, werden Sie wahrscheinlich besser, einen eigenen Befehl gleichzeitig sein. Sie können den Code von Klonen **CMDIFrameWnd::OnWindowNew** und ändern sie die bestimmten Frame und Ansicht-Klassen der Elemente wie gewünscht.  
  
-   ID_WINDOW_ARRANGE Ordnet Symbole im unteren Bereich des MDI-Fensters.  
  
     `CMDIFrameWnd` Dieser standard MDI-Befehl in eine Hilfsfunktion Implementierung implementiert **OnMDIWindowCmd**. Dieses Hilfsprogramm MDI-Fenster Nachrichten Befehls-IDs zugeordnet und kann daher viel Code austauschen.  
  
     Wie die meisten Befehle für MDI-Fenster im Menü ist der Befehl deaktiviert, wenn keine aktives untergeordnete MDI-Fenster vorhanden ist.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_WINDOW_CASCADE überlappend Fenster überlappend.  
  
     `CMDIFrameWnd` Dieser standard MDI-Befehl in eine Hilfsfunktion Implementierung implementiert **OnMDIWindowCmd**. Dieses Hilfsprogramm MDI-Fenster Nachrichten Befehls-IDs zugeordnet und kann daher viel Code austauschen.  
  
     Wie die meisten Befehle für MDI-Fenster im Menü ist der Befehl deaktiviert, wenn keine aktives untergeordnete MDI-Fenster vorhanden ist.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_WINDOW_TILE_HORZ Kacheln Windows horizontal.  
  
     Mit diesem Befehl wird im implementiert `CMDIFrameWnd` wie **ID_WINDOW_CASCADE**, außer dass eine andere Meldung von MDI-Fenster für den Vorgang verwendet wird.  
  
     Sie sollten die standardausrichtung für die Kachel für die Anwendung auswählen. Hierzu können Sie durch die ID für das Fenster "Kachel" Menüelement entweder ändern **ID_WINDOW_TILE_HORZ** oder **ID_WINDOW_TILE_VERT**.  
  
-   ID_WINDOW_TILE_VERT Kacheln Windows vertikal.  
  
     Mit diesem Befehl wird im implementiert `CMDIFrameWnd` wie **ID_WINDOW_CASCADE**, außer dass eine andere Meldung von MDI-Fenster für den Vorgang verwendet wird.  
  
     Sie sollten die standardausrichtung für die Kachel für die Anwendung auswählen. Hierzu können Sie durch die ID für das Fenster "Kachel" Menüelement entweder ändern **ID_WINDOW_TILE_HORZ** oder **ID_WINDOW_TILE_VERT**.  
  
-   ID_WINDOW_SPLIT Tastaturschnittstelle mit Splitter.  
  
     `CView` behandelt diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Sicht ein unterteiltes Fenster gehört, wird mit diesem Befehl an die Funktion für die Implementierung delegieren `CSplitterWnd::DoKeyboardSplit`. Dies abzulegen des Splitters in einem Modus, die Benutzern teilen oder einem Splitterfenster Aufteilung Tastatur zulässt.  
  
     Dieser Befehl ist deaktiviert, wenn die Sicht nicht in eine Aufteilung ist.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_APP_ABOUT wird das Dialogfeld "Info" aufgerufen.  
  
     Es ist keine Standardimplementierung für eine Anwendung Info-Dialogfeld. Die Standardeinstellung von AppWizard erstellte Anwendung eine benutzerdefinierte Dialogfeldklasse für Ihre Anwendung erstellt und als die Info-Dialogfeld verwenden. AppWizard wird auch triviale Befehlshandler schreiben, die mit diesem Befehl verarbeitet und ruft das Dialogfeld ".  
  
     Implementieren Sie fast immer mit diesem Befehl.  
  
-   ID_APP_EXIT Beenden der Anwendung.  
  
     **CWinApp::OnAppExit** verarbeitet mit diesem Befehl durch Senden einer `WM_CLOSE` Nachricht im Hauptfenster der Anwendung. Der Standard Herunterfahren der Anwendung (aufzufordern für fehlerhafte Dateien usw.) erfolgt durch die `CFrameWnd` Implementierung.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen. Überschreiben von `CWinApp::SaveAllModified` oder `CFrameWnd` schließende Logik wird empfohlen.  
  
     Wenn Sie mit diesem Befehl implementieren möchten, empfehlen wir dieses Befehls-ID verwendet wird.  
  
-   ID_HELP_INDEX listet Hilfethemen aus. HLP-Datei.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnHelpIndex` mit diesem Befehl behandelt, durch den Aufruf Trivial `CWinApp::WinHelp`.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_HELP_USING Zeigt Hilfe zur Verwendung der Hilfe an.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnHelpUsing` mit diesem Befehl behandelt, durch den Aufruf Trivial `CWinApp::WinHelp`.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_CONTEXT_HELP eingibt UMSCHALT + F1 Hilfemodus.  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnContextHelp` Der Hilfecursor Modus festlegen, eine modale Größenanpassungsschleife eingeben und warten, bis des Benutzers zur Auswahl eines Fensters, um Hilfe zu erhalten, auf, um mit diesem Befehl verarbeitet. Finden Sie unter [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) detaillierte Informationen auf die Hilfe von MFC-Implementierung.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_HELP bietet Hilfe für den aktuellen Kontext  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     `CWinApp::OnHelp` verarbeitet mit diesem Befehl die richtige Hilfe-Kontext für den aktuellen Anwendungskontext abrufen. Einfache F1-Hilfe verarbeitet, die in den Meldungsfeldern und so weiter. Finden Sie unter [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für weitere Details auf die MFC-Bibliothek bei der Implementierung.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_DEFAULT_HELP Zeigt Hilfe an Standardeinstellung für den Kontext  
  
    > [!NOTE]
    >  Sie müssen diese Option, um eine Verbindung Ihrer `CWinApp`-abgeleitete Klasse-meldungszuordnung, um diese Funktion zu aktivieren.  
  
     Mit diesem Befehl wird in der Regel zugeordnet `CWinApp::OnHelpIndex`.  
  
     Ein anderen Befehlshandler kann angegeben werden, ggf. eine Unterscheidung zwischen Standard-Hilfe und im Hilfe-Index.  
  
-   ID_NEXT_PANE wechselt zum nächsten Bereich  
  
     `CView` behandelt diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Sicht ein unterteiltes Fenster gehört, wird mit diesem Befehl an die Funktion für die Implementierung delegieren **CSplitterWnd::OnNextPaneCmd**. Dadurch wird die aktive Ansicht zum nächsten Bereich in der Splitter verschoben.  
  
     Dieser Befehl ist deaktiviert, wenn die Sicht nicht in eine Aufteilung kann oder es keine nächsten Bereich ist zu wechseln.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_PREV_PANE wechselt zum vorherigen Bereich  
  
     `CView` behandelt diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Sicht ein unterteiltes Fenster gehört, wird mit diesem Befehl an die Funktion für die Implementierung delegieren **CSplitterWnd::OnNextPaneCmd**. Dadurch wird die aktive Ansicht zum vorherigen Bereich in der Splitter verschoben.  
  
     Dieser Befehl ist deaktiviert, wenn die Sicht nicht in eine Aufteilung kann oder es keine vorherigen Bereich ist zu wechseln.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_OLE_INSERT_NEW Fügt ein neues OLE-Objekt  
  
     Derzeit ist keine Standardimplementierung für diesen Befehl. Sie müssen dies für Implementieren Ihrer `CView`-abgeleitete Klasse, um ein neues OLE-Element/Objekt an der aktuellen Auswahl einzufügen.  
  
     Alle OLE-Clientanwendungen sollten diesen Befehl implementieren. AppWizard, mit der OLE-Option erstellt eine Skelette-Implementierung der **OnInsertObject** in Ihrer Ansichtsklasse, die Sie abgeschlossen hat.  
  
     Finden Sie im MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) Beispiel für eine vollständige Implementierung dieses Befehls.  
  
-   ID_OLE_EDIT_LINKS bearbeitet OLE-links  
  
     `COleDocument` verarbeitet mit diesem Befehl unter Verwendung der bereitgestellten MFC-Implementierung des Dialogfelds "standard OLE-Links. Die Implementierung dieser Dialog erfolgt über die `COleLinksDialog` Klasse. Wenn das aktuelle Dokument keine Links enthält, wird der Befehl deaktiviert.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   ID_OLE_VERB_FIRST... LETZTE eine ID-Bereich für OLE-Verben  
  
     `COleDocument` Mithilfe dieses Befehls-ID-Bereich für die Verben, die von der aktuell ausgewählten OLE-Element/Objekt unterstützt. Dies muss ein Bereich sein, da ein angegebener OLE-Element/Objekttyp NULL oder mehr benutzerdefinierte Verben unterstützen kann. In der Anwendung im Menü haben Sie die ein Menüelement mit der ID **ID_OLE_VERB_FIRST**. Wenn das Programm ausgeführt wird, wird das Menü mit der entsprechenden Verb menübeschreibung (oder ein Popupmenü mit vielen Verben) aktualisiert werden. Die Verwaltung des OLE-Menüs erfolgt durch `AfxOleSetEditMenu`, in der Update-Befehlshandler Benutzeroberfläche für diesen Befehl "Fertig" ändert.  
  
     Es gibt keine explizite Befehlshandler für die Verarbeitung jedes Befehls-ID in diesem Bereich aus. **COleDocument::OnCmdMsg** überschrieben wird, um alle Befehls-IDs in diesem Bereich abfangen, in nullbasierte Verb Zahlen zu aktivieren und starten Sie den Server für das jeweilige Verb (mit `COleClientItem::DoVerb`).  
  
     Die Anpassung oder sonstigen Nutzung des dieses Befehls-ID-Bereich wird nicht empfohlen.  
  
-   ID_VIEW_TOOLBAR Schaltet die Symbolleiste ein- oder ausschalten  
  
     `CFrameWnd` verarbeitet mit diesem Befehl und die Update-Befehlshandler UI, um den sichtbaren Zustand der Symbolleiste zu wechseln. Die Symbolleiste muss ein untergeordnetes Fenster des Frames mit der untergeordneten Fenster ID `AFX_IDW_TOOLBAR`. Der Befehlshandler schaltet tatsächlich die Sichtbarkeit des Fensters Symbolleiste. `CFrameWnd::RecalcLayout` wird verwendet, das Rahmenfenster über die Symbolleiste im neuen Zustand neu zeichnet. Die UI-Update-Befehlshandler überprüft das Menüelement aus, wenn die Symbolleiste angezeigt wird.  
  
     Anpassung von diesem Befehlshandler wird nicht empfohlen. Wenn Sie die zusätzliche Symbolleisten hinzufügen möchten, sollten Sie zum Klonen und Ändern der Befehlshandler und Update-Benutzeroberfläche Befehlshandler für diesen Befehl.  
  
-   ID_VIEW_STATUS_BAR Schaltet die Statusleiste ein- oder ausschalten  
  
     Mit diesem Befehl wird im implementiert `CFrameWnd` ebenso wie **ID_VIEW_TOOLBAR**, mit Ausnahme von einer anderen untergeordneten Fenster-ID (**AFX_IDW_STATUS_BAR**) verwendet wird.  
  
## <a name="update-only-command-handlers"></a>Nur-Update-Befehlshandler  
 Mehrere Standardbefehls-IDs werden als Indikatoren in Statusleisten verwendet. Diese verwenden die gleiche Updatebefehl UI-Mechanismus zur Behandlung von ihren aktuellen visuellen Status während der Leerlaufzeit Anwendung angezeigt. Da nicht vom Benutzer ausgewählt werden (d. h. Sie können keine Status-Leistenbereich push), und klicken Sie dann keinen Sinn, haben ein `ON_COMMAND` Handler für diese Befehls-IDs.  
  
-   **ID_INDICATOR_CAPS** : CAP Sperrindikator.  
  
-   **ID_INDICATOR_NUM** : NUM Sperrindikator.  
  
-   **ID_INDICATOR_SCRL** : Kap-Sperrindikator.  
  
-   **ID_INDICATOR_KANA** : KANA Sperrindikator (gilt nur für Japanisch Systeme).  
  
 Alle drei der folgenden in implementiert **CFrameWnd::OnUpdateKeyIndicator**, eine Implementierung-Hilfe, die die Befehls-ID verwendet wird, um den entsprechenden virtuellen Schlüssel zuzuordnen. Eine verbreitete Implementierung aktiviert oder deaktiviert (für Statusbereiche deaktiviert = kein Text) der `CCmdUI` Objekt abhängig davon, ob die entsprechende virtuelle Taste zurzeit gesperrt ist.  
  
 Anpassung von diesem Befehlshandler wird nicht empfohlen.  
  
-   **ID_INDICATOR_EXT: EXT**beendete select Indikator.  
  
-   **ID_INDICATOR_OVR: Bereitstellungszeitpunkt**e**R**Indikator zu erreichen.  
  
-   **ID_INDICATOR_REC: REC**Ording Indikator.  
  
 Derzeit ist keine Standardimplementierung für diese Indikatoren.  
  
 Wenn Sie diese Indikatoren implementieren möchten, wird empfohlen, diese Symbol-IDs und verwalten, die Reihenfolge der Indikatoren in der Statusleiste (d. h. in dieser Reihenfolge: EXT, CAP, NUM, Kap-, ÜB, MAK).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

