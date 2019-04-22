---
title: 'TN022: Standardbefehlen'
ms.date: 11/04/2016
f1_keywords:
- vc.commands
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
ms.openlocfilehash: 8d568760cc75a4c1f2ddb6dd88108cc830783194
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775830"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Standardbefehlen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt die Standardbefehle-Implementierungen von MFC 2.0 bereitgestellt werden. Lesen [technischen Hinweis 21](../mfc/tn021-command-and-message-routing.md) zuerst, da es wird, die Mechanismen verwendet beschrieben, um viele der standard-Befehle implementieren.

Diese Beschreibung wird davon ausgegangen, Kenntnisse der MFC-Architekturen, die APIs und die üblichen Programmierpraxis. Dokumentierte als auch nicht dokumentierte "Implementation nur" werden APIs beschrieben. Dies ist kein Ausgangspunkt, mehr über die Features von oder Programmieren in MFC. Finden Sie unter Visual C++ für weitere allgemeine Informationen und Details der dokumentierten APIs.

## <a name="the-problem"></a>Das Problem

MFC definiert viele Standardbefehls-IDs in der Headerdatei AFXRES. H. Framework-Unterstützung für diese Befehle variiert. Verstehen, wo und wie die Framework-Klassen dieser Befehle verarbeiten, die zeigt nicht nur Ihnen wie das Framework intern funktioniert, jedoch bietet nützlichsten Informationen zum Anpassen von den standardimplementierungen, und erfahren Sie, einige Techniken zum Implementieren von eigene Befehlshandler.

## <a name="contents-of-this-technical-note"></a>Inhalt dieses technischer Hinweis

Jedes Befehls-ID wird in beiden Abschnitten beschrieben:

- Titel: der symbolische Namen der Befehls-ID (z. B. ID_FILE_SAVE) gefolgt von den Zweck des Befehls (z. B. "speichert das aktuelle Dokument") durch einen Doppelpunkt getrennt.

- Eine oder mehrere Absätze, beschreibt die Klassen implementieren, mit dem Befehl, und was bewirkt, dass die standardmäßige Implementierung

Die meisten Implementierungen von Standard-Befehl werden in die Framework Basisklasse meldungszuordnung prewired. Es gibt einige Befehl-Implementierungen, die explizite Verknüpfung in der abgeleiteten Klasse erfordern. Diese werden unter "Hinweis" beschrieben. Wenn Sie die richtigen Optionen in AppWizard ausgewählt haben, werden diese Standardhandler für die Sie in das generierte Anwendungsgerüst verbunden.

## <a name="naming-convention"></a>Namenskonvention

Standard-Befehle führen Sie eine einfache Benennungskonvention, die wir empfehlen, dass Sie nach Möglichkeit verwenden. Die meisten Befehle befinden sich im standard stellen in der Menüleiste der Anwendung. Die symbolische Namen des Befehls beginnt mit "ID_" gefolgt vom Namen standard-Popup-Menü, gefolgt vom Namen Menüelements. Die symbolische Namen ist in Großbuchstaben mit Wörtern Unterstrich. Für Befehle, die nicht über Elementnamen Standardmenü verfügen, ist ein logische Befehlsnamen beginnend mit "ID_" (z. B. ID_NEXT_PANE) definiert.

Wir verwenden das Präfix "ID_", um die Befehle angeben, die entwickelt wurden, Menüelemente, Symbolleisten-Schaltflächen oder anderen Benutzeroberflächen-Befehl gebunden werden soll. Behandlung von Befehlen mit "ID_" Befehlshandler sollte die ON_COMMAND- und ON_UPDATE_COMMAND_UI Mechanismen von der MFC-befehlsarchitektur verwendet werden.

Es wird empfohlen, dass Sie das standardmäßige "IDM_"-Präfix für Menüelemente verwenden, die nicht der-befehlsarchitektur folgen und im Menü-spezifischen Code zum Aktivieren und deaktivieren sie benötigen. Die Anzahl der bestimmte Befehle im Menü sollte natürlich klein sein, da der MFC-befehlsarchitektur folgen, nicht nur Befehlshandler leistungsfähiger macht (da sie mit Symbolleisten funktionieren), sondern die befehlshandlercode ein wiederverwendet werden macht.

## <a name="id-ranges"></a>ID-Bereiche

Näheres [technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) für Weitere Informationen zur Verwendung von MFC-ID-Bereiche.

MFC-Standardbefehle liegen im Bereich von 0xE000 zu 0xEFFF. Sie verlassen Sie sich nicht auf die speziellen Werte, der diese IDs unterliegt in zukünftigen Versionen der Bibliothek enthalten, werden.

Ihre Anwendung sollte die Befehle im Bereich von 0 x 8000 bis 0xDFFF definieren.

## <a name="standard-command-ids"></a>Standardbefehle-IDs

Für jedes Befehls-ID befindet sich eine Standardnachricht Zeile Eingabeaufforderung Zeichenfolge, die in die Datei ANWEISUNGEN gefunden werden kann. RC. Die Zeichenfolgen-ID für diese Eingabeaufforderung im Menü muss identisch mit der Befehls-ID sein.

- ID_FILE_NEW erstellt ein neues /-leeres Dokument.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnFileNew` Dieser Befehl hängt die Anzahl der Dokumentvorlagen implementiert in der Anwendung. Wenn es nur eine `CDocTemplate`, `CWinApp::OnFileNew` erstellt ein neues Dokument dieses Typs als auch die richtige Frame und Ansicht-Klasse.

   Wenn es mehr als eine `CDocTemplate`, `CWinApp::OnFileNew` fordert den Benutzer ein Dialogfeld (AFX_IDD_NEWTYPEDLG), sodass sie Sie auswählen, welche die zu verwendende Typ zu dokumentieren. Die ausgewählte `CDocTemplate` wird verwendet, um das Dokument zu erstellen.

   Eine häufige Anpassung der ID_FILE_NEW ist, eine andere und mehr grafische Auswahl Dokumenttypen bereitzustellen. In diesem Fall können implementieren Sie Ihr eigenes `CMyApp::OnFileNew` und platzieren Sie sie in der meldungszuordnung anstelle von `CWinApp::OnFileNew`. Es gibt keine Notwendigkeit, Implementierung der Basisklasse aufzurufen.

   Geben Sie einen separaten Befehl zum Erstellen eines Dokuments für jeden Typ ist eine weitere häufige Anpassung der ID_FILE_NEW werden. In diesem Fall sollten Sie die neuen Befehls-IDs, z. B. ID_FILE_NEW_CHART und ID_FILE_NEW_SHEET definieren.

- ID_FILE_OPEN öffnet ein vorhandenes Dokument.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnFileOpen` verfügt über eine sehr einfache Implementierung eines Aufrufs `CWinApp::DoPromptFileName` gefolgt von `CWinApp::OpenDocumentFile` durch die Datei oder Pfad des zu öffnenden Datei. Die `CWinApp` Implementierung Routine `DoPromptFileName` wird das Standarddialogfeld FileOpen und füllt sie mit der Dateierweiterungen, die von der aktuellen Dokumentvorlagen abgerufen.

   Eine häufige Anpassung der ID_FILE_OPEN ist das Dialogfeld "FileOpen" anpassen oder zusätzliche Filter hinzufügen. Ersetzen Sie die standardmäßige Implementierung mit Ihren eigenen FileOpen-Dialogfeld, und rufen ist die empfohlene Methode zum Anpassen dieser `CWinApp::OpenDocumentFile` mit den Namen des Dokuments Datei oder Pfad. Es gibt keine Notwendigkeit, die Basisklasse aufzurufen.

- ID_FILE_CLOSE schließt die derzeit geöffnete Dokument.

   `CDocument::OnFileClose` Aufrufe `CDocument::SaveModified` , die der Benutzer aufgefordert, das Dokument zu speichern, wenn es geändert wurde, und dann ruft `OnCloseDocument`. Alle schließen Logik, einschließlich der Zerstören des Dokuments, erfolgt in der `OnCloseDocument` Routine.

    > [!NOTE]
    >  ID_FILE_CLOSE fungiert, anders als eine WM_CLOSE-Meldung oder einen SC_CLOSE-System-Befehl an das Rahmenfenster Dokumente gesendet. Schließen eines Fensters wird das Dokument geschlossen werden, nur wenn dieser das letzte Frame-Fenster mit das Dokument ist. Schließen des Dokuments mit ID_FILE_CLOSE nicht nur das Dokument geschlossen, aber wird beendet, dass alle Rahmenfenster des Dokuments angezeigt.

- ID_FILE_SAVE speichert das aktuelle Dokument.

   Verwendet die Implementierung eine Hilfsroutine `CDocument::DoSave` für beide dient `OnFileSave` und `OnFileSaveAs`. Wenn Sie ein Dokument speichern, die noch nicht gespeichert wurde (d. h. es keinen Pfadnamen ein, wie im Fall von FileNew) oder, der aus einem nur-Lese Dokument gelesen wurde die `OnFileSave` Logik angewendet wird, wie die ID_FILE_SAVE_AS-Befehl aus, und bitten Sie den Benutzer auf einen neuen Dateinamen anzugeben. . Der eigentliche Prozess der Öffnen der Datei, und dies das Speichern erfolgt über die virtuelle Funktion `OnSaveDocument`.

   Es gibt zwei häufige Gründe für die ID_FILE_SAVE anpassen. Entfernen Sie für Dokumente, die nicht speichern einfach die ID_FILE_SAVE-Menüelemente und Symbolleisten-Schaltflächen, von der Benutzeroberfläche. Stellen Sie außerdem sicher, dass Sie niemals Ihr Dokument geändert (d. h. niemals Aufrufen `CDocument::SetModifiedFlag`) und das Framework wird niemals dazu führen, dass das Dokument gespeichert werden soll. Definieren Sie einen neuen Befehl für diesen Vorgang für Dokumente, die an einem beliebigen Ort als Datei auf einem Datenträger speichern.

   Im Fall von einem `COleServerDoc`, ID_FILE_SAVE wird verwendet, für die Datei speichern (für normale Dokumente) und Aktualisierung der (für eingebettete Dokumente).

   Wenn die Dokumentdaten in einzelnen Datenträger-Dateien gespeichert, aber nicht die Standardeinstellung verwenden möchten `CDocument` Implementierung zu serialisieren, sollten Sie überschreiben `CDocument::OnSaveDocument` anstelle von `OnFileSave`.

- ID_FILE_SAVE_AS speichert das aktuelle Dokument unter einem anderen Dateinamen an.

   Die `CDocument::OnFileSaveAs` Implementierung verwendet die gleichen `CDocument::DoSave` Hilfsroutine als `OnFileSave`. Die `OnFileSaveAs` Befehl erfolgt genauso ID_FILE_SAVE hätte die Dokumente keine Dateinamen vor dem Speichern. `COleServerDoc::OnFileSaveAs` implementiert die Logik, eine normales Dokument-Datendatei speichern oder Speichern eines Serverdokuments, die in einer anderen Anwendung als separate Datei eingebetteten OLE-Objekt darstellt.

   Wenn Sie die Logik der ID_FILE_SAVE anpassen, Sie werden wahrscheinlich ID_FILE_SAVE_AS auf ähnliche Weise anpassen möchten, oder der Vorgang von "Speichern unter" gilt möglicherweise nicht in Ihr Dokument. Sie können dem Menüelement, das in der Menüleiste entfernen, wenn es nicht erforderlich ist.

- ID_FILE_SAVE_COPY_AS speichert eine Kopie für die aktuellen Dokument unter einem neuen Namen.

   Die `COleServerDoc::OnFileSaveCopyAs` Implementierung ist sehr ähnlich `CDocument::OnFileSaveAs`, außer dass das Document-Objekt nicht "an die zugrunde liegende Datei nach dem Speichern angefügt ist". D. h., wenn das Dokument im Arbeitsspeicher "vor dem Speichern geändert wurde", ist es immer noch "geändert". Darüber hinaus hat mit diesem Befehl keine Auswirkungen auf den Pfadnamen oder den Titel in das Dokument gespeichert werden.

- ID_FILE_UPDATE benachrichtigt den Container aus, um ein eingebettetes Dokument zu speichern.

   Die `COleServerDoc::OnUpdateDocument` Implementierung einfach Notifiies den Container, der die Einbettung gespeichert werden soll. Der Container ruft dann die entsprechenden OLE-APIs, um das eingebettete Objekt zu speichern.

- ID_FILE_PAGE_SETUP Ruft einen anwendungsspezifischen Seite Setup/Layout-Dialog.

   Derzeit ist es jedoch keinen Standard für diesen Dialog, und das Framework keine Standardimplementierung dieses Befehls besitzt.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_FILE_PRINT_SETUP rufen Sie das Standarddialogfeld einrichten.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   Dieser Befehl ruft das Dialogfeld "Drucken Standardinstallation", mit dem Benutzer zum Anpassen des Druckers, und Drucken die Einstellungen für die mindestens, in diesem Dokument oder höchstens alle Dokumente in dieser Anwendung. Sie müssen die Systemsteuerung verwenden, um die standarddruckereinstellungen für das gesamte System zu ändern.

   `CWinApp::OnFilePrintSetup` verfügt über eine sehr einfache Implementierung erstellen eine `CPrintDialog` -Objekt ab, und rufen die `CWinApp::DoPrintDialog` implementierungsfunktion. Hiermit wird die Standard-Drucker Anwendungsinstallation.

   Die allgemeine Notwendigkeit zum Anpassen von mit diesem Befehl ist für die Druckereinstellungen für pro-Dokument, die mit dem Dokument beim Speichern gespeichert werden soll. Dazu sollten Sie in der meldungszuordnung Handler in Hinzufügen Ihrer `CDocument` Klasse, die erstellt eine `CPrintDialog` Objekt, initialisiert es mit den entsprechenden Drucker-Attributen (in der Regel *hDevMode-Feld* und *hDevNames*), rufen Sie die `CPrintDialog::DoModal`, und speichern Sie die geänderte Druckereinstellungen. Für eine stabile Implementierung sollten Sie die Implementierung der zunächst `CWinApp::DoPrintDialog` zum Erkennen von Fehlern und `CWinApp::UpdatePrinterSelection` arbeiten mit sinnvollen Standardwerten Behandlung und Nachverfolgen von Änderungen für eine systemweite Drucker.

- ID_FILE_PRINT Standard Drucken des aktuellen Dokuments

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CView`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   Mit diesem Befehl wird das aktuelle Dokument gedruckt oder genauer gesagt, beginnt den Druckvorgang, der dies erfordert das standardmäßige Dialogfeld "Drucken" aufrufen und die print-Engine ausgeführt.

   `CView::OnFilePrint` mit diesem Befehl und die print-Hauptschleife implementiert werden. Ruft den virtuellen `CView::OnPreparePrinting` auf Aufforderung des Benutzers mit dem Dialogfeld "Drucken". Klicken Sie dann bereitet die DC-Ausgabe an den Drucker zu wechseln, wird das Drucken Statusdialogfeld (AFX_IDD_PRINTDLG) und sendet die `StartDoc` ESC, um den Drucker. `CView::OnFilePrint` enthält auch die wichtigsten seitenbasierten print, Loop. Für jede Seite ruft den virtuellen `CView::OnPrepareDC` gefolgt von einem `StartPage` Escapezeichen und Aufrufen der virtuellen `CView::OnPrint` für diese Seite. Wenn Sie fertig sind, die virtuelle `CView::OnEndPrinting` aufgerufen wird, und das Dialogfeld "Drucken Status" geschlossen ist.

   Die MFC-Druck-Architektur soll auf viele verschiedene Arten für Drucken und Druckvorschau zu verknüpfen. Normalerweise finden Sie die verschiedenen `CView` überschreibbare-Funktionen für alle Seiten orientiert Druckaufgaben ausreichend. Nur bei Anwendungen, die der Drucker für objektorientierte nicht-Page-Ausgabe verwendet, sollten Sie die Notwendigkeit, ersetzen Sie die Implementierung ID_FILE_PRINT suchen.

- ID_FILE_PRINT_PREVIEW Geben Sie den Seitenansicht-Modus für das aktuelle Dokument.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CView`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CView::OnFilePrintPreview` Startet den Seitenansichtmodus durch Aufrufen der Hilfsfunktion für das dokumentierte `CView::DoPrintPreview`. `CView::DoPrintPreview` ist die Haupt-Engine für die Seitenansicht-Schleife, ebenso `OnFilePrint` ist die Haupt-Engine für die Drucken-Schleife.

   Die Seitenansicht-Vorgang kann in einer Vielzahl von Möglichkeiten angepasst werden, durch das Übergeben von unterschiedlichen Parameters `DoPrintPreview`. Näheres [technischen Hinweis 30](../mfc/tn030-customizing-printing-and-print-preview.md), einige Details der Seitenansicht erläutert und wie Sie sie anpassen.

- ID_FILE_MRU_FILE1... FILE16 Einen Bereich von Befehls-IDs für das MRU-Menü Datei **Liste**.

   `CWinApp::OnUpdateRecentFileMenu` ist ein Update UI Befehlshandler, der die fortgeschrittenere Verwendungen des ON_UPDATE_COMMAND_UI-Mechanismus. In der Menüressource müssen Sie nur ein einzelnes Menüelement mit der ID ID_FILE_MRU_FILE1 definieren. Dieses Menüelement bleibt zunächst deaktiviert.

   Als das MRU-Menü wächst, Menü "Weitere", die Elemente der Liste hinzugefügt werden. Der Standard `CWinApp` Implementierung ist standardmäßig auf den standardmäßigen Grenzwert der vier zuletzt verwendeten Dateien. Sie können die Standardeinstellung ändern, durch den Aufruf `CWinApp::LoadStdProfileSettings` mit einem Wert größer oder kleiner. Die MRU-Liste ist in der Anwendung gespeichert. INI-Datei. Die Liste wird in der Anwendungsverzeichnis geladen `InitInstance` ausgeführt werden, wenn Sie aufrufen `LoadStdProfileSettings`, und wird gespeichert, wenn die Anwendung beendet wird. Die MRU-Menü Update Befehlshandler Benutzeroberfläche werden auch absolute Pfade, relative Pfade für die Anzeige auf das Menü "Datei" konvertiert werden.

   `CWinApp::OnOpenRecentFile` ist der ON_COMMAND-Handler, der den eigentlichen Befehl ausführt. Ruft einfach den Dateinamen aus der MRU-Liste und Aufrufe `CWinApp::OpenDocumentFile`, die alle Aktionen zum Öffnen der Datei und die MRU-Liste aktualisiert wird.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_EDIT_CLEAR löscht die aktuelle Auswahl

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls mit `CEdit::Clear`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_CLEAR_ALL löscht das gesamte Dokument.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID. Finden Sie im Tutorial für MFC-Beispiel [SCRIBBLE](../overview/visual-cpp-samples.md) eine beispielimplementierung.

- ID_EDIT_COPY kopiert die aktuelle Auswahl in die Zwischenablage.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls, der den derzeitig markierten Text als HIERSVR mit in die Zwischenablage kopiert `CEdit::Copy`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_CUT schneidet die aktuelle Auswahl in die Zwischenablage.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung von diesem Befehl, der den derzeitig markierten Text in die Zwischenablage, wie die Verwendung von HIERSVR schneidet `CEdit::Cut`. Der Befehl ist deaktiviert, wenn keine aktuelle Auswahl vorhanden ist.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_FIND beginnt die Suche wird, wird das Dialogfeld ohne Modus suchen.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls, der die Hilfsfunktion Implementierung aufruft `OnEditFindReplace` verwenden und die vorherigen Einstellungen für den Suchen/Ersetzen in privaten implementierungsvariablen zu speichern. Die `CFindReplaceDialog` Klasse wird verwendet, um das Dialogfeld ohne Modus für die Aufforderung an den Benutzer zu verwalten.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_PASTE fügt den aktuellen Inhalt der Zwischenablage ein.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung von diesem Befehl, der aktuellen Daten in der Zwischenablage und Ersetzen Sie dabei mit den ausgewählten Text kopiert `CEdit::Paste`. Der Befehl ist deaktiviert, wenn keine **HIERSVR** in die Zwischenablage.

   `COleClientDoc` bietet nur einen Update-Befehlshandler Benutzeroberfläche für diesen Befehl ein. Wenn die Zwischenablage nicht eingebettet werden OLE-Element/Objekt enthält, wird der Befehl deaktiviert. Sie sind verantwortlich für das Schreiben des Handlers für die eigentliche Befehl, um das eigentliche einfügen. Wenn OLE-Anwendungen auch andere Formate einfügen kann, sollten Sie Ihre eigenen Update-Befehlshandler-Benutzeroberfläche in Ihrer Ansicht oder das Dokument bereitstellen (d. h. an einer beliebigen Stelle vor dem `COleClientDoc` in das Ziel Befehlsrouting).

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

   Verwenden Sie zum Ersetzen der standard OLE-Implementierung, `COleClientItem::CanPaste`.

- ID_EDIT_PASTE_LINK Fügt einen Link aus dem aktuellen Inhalt der Zwischenablage ein.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `COleDocument` bietet nur einen Update-Befehlshandler Benutzeroberfläche für diesen Befehl ein. Wenn die Zwischenablage nicht verknüpfbares OLE/Elementobjekt enthält, wird der Befehl deaktiviert. Sie sind verantwortlich für das Schreiben des Handlers für die eigentliche Befehl, um das eigentliche einfügen. Wenn OLE-Anwendungen auch andere Formate einfügen kann, sollten Sie Ihre eigenen Update-Befehlshandler-Benutzeroberfläche in Ihrer Ansicht oder das Dokument bereitstellen (d. h. an einer beliebigen Stelle vor dem `COleDocument` in das Ziel Befehlsrouting).

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

   Verwenden Sie zum Ersetzen der standard OLE-Implementierung, `COleClientItem::CanPasteLink`.

- ID_EDIT_PASTE_SPECIAL fügt den aktuellen Inhalt der Zwischenablage mit Optionen.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse. MFC bietet dieses Dialogfeld nicht.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_REPEAT wiederholt den letzten Vorgang.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls, den letzten Find-Vorgang zu wiederholen. Die private Implementierung-Variablen für die letzten Find dienen. Der Befehl ist deaktiviert, wenn eine Suche kann nicht ausgeführt werden.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_REPLACE beginnt der Ersetzungsvorgang wird das Dialogfeld ohne Modus ersetzen.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls, der die Hilfsfunktion Implementierung aufruft `OnEditFindReplace` verwenden und die vorherigen Einstellungen für den Suchen/Ersetzen in privaten implementierungsvariablen zu speichern. Die `CFindReplaceDialog` Klasse wird verwendet, um den nicht-modales Dialogfeld verwalten, die der Benutzer aufgefordert wird.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_SELECT_ALL wählt das gesamte Dokument.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls, in dem der gesamte Text im Dokument ausgewählt. Der Befehl ist deaktiviert, wenn kein Text Auswahl vorhanden ist.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_UNDO macht den letzten Vorgang rückgängig.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   `CEditView` Stellt eine Implementierung dieses Befehls mit `CEdit::Undo`. Der Befehl ist deaktiviert, wenn `CEdit::CanUndo` gibt FALSE zurück.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_EDIT_REDO wiederholt den letzten Vorgang.

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen dies implementieren, für die einzelnen `CView`-abgeleitete Klasse.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_WINDOW_NEW öffnet ein weiteres Fenster auf dem aktiven Dokument.

   `CMDIFrameWnd::OnWindowNew` implementiert dieses leistungsfähige Feature mit, dass die Dokumentvorlage des aktuellen Dokuments um einen anderen Frame mit einer anderen Ansicht des aktuellen Dokuments zu erstellen.

   Wie die meisten mehrerer Document Interface (MDI) Fenster Menübefehle wird der Befehl deaktiviert, wenn keine aktiven untergeordneten MDI-Fensters.

   Anpassung von diesen Befehlshandler wird nicht empfohlen. Wenn Sie möchten einen Befehl angeben, der zusätzliche Ansichten oder Rahmenfenster erstellt, werden Sie wahrscheinlich besser, entwickeln Ihre eigenen Befehls sein. Sie können den Code aus Klonen `CMDIFrameWnd::OnWindowNew` und ändern sie die der bestimmten Frame und Anzeigen von Klassen Ihrer Wahl.

- ID_WINDOW_ARRANGE richtet die Symbole am unteren Rand eines MDI-Fensters.

   `CMDIFrameWnd` Dieser standard MDI-Befehl in eine Hilfsfunktion Implementierung implementiert `OnMDIWindowCmd`. Dieses Hilfsprogramm Befehls-IDs für MDI-Windows-Nachrichten zugeordnet und kann daher viel Code gemeinsam.

   Der Befehl ist wie die meisten Befehle für MDI-Fensters im Menü deaktiviert, es ist keine aktiven untergeordneten MDI-Fensters.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_WINDOW_CASCADE kaskadierende Windows, um eine Überlappung.

   `CMDIFrameWnd` Dieser standard MDI-Befehl in eine Hilfsfunktion Implementierung implementiert `OnMDIWindowCmd`. Dieses Hilfsprogramm Befehls-IDs für MDI-Windows-Nachrichten zugeordnet und kann daher viel Code gemeinsam.

   Der Befehl ist wie die meisten Befehle für MDI-Fensters im Menü deaktiviert, es ist keine aktiven untergeordneten MDI-Fensters.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_WINDOW_TILE_HORZ   Tiles windows horizontally.

   Mit diesem Befehl wird in implementiert `CMDIFrameWnd` wie ID_WINDOW_CASCADE, außer dass eine andere MDI-Windows-Meldung für den Vorgang verwendet wird.

   Sie sollten die standardausrichtung für die Kachel für Ihre Anwendung auswählen. Dies ist möglich, indem Sie die ID für das Fenster "Kachel" Menüelement ID_WINDOW_TILE_HORZ oder ID_WINDOW_TILE_VERT ändern.

- ID_WINDOW_TILE_VERT-Kacheln Windows vertikal.

   Mit diesem Befehl wird in implementiert `CMDIFrameWnd` wie ID_WINDOW_CASCADE, außer dass eine andere MDI-Windows-Meldung für den Vorgang verwendet wird.

   Sie sollten die standardausrichtung für die Kachel für Ihre Anwendung auswählen. Dies ist möglich, indem Sie die ID für das Fenster "Kachel" Menüelement ID_WINDOW_TILE_HORZ oder ID_WINDOW_TILE_VERT ändern.

- ID_WINDOW_SPLIT-Tastatur-Schnittstelle, die Aufteilung.

   `CView` verarbeitet diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Ansicht eines unterteilten Fensters gehört, wird mit diesem Befehl an die implementierungsfunktion Delegieren `CSplitterWnd::DoKeyboardSplit`. Dies platziert den Splitter in einem Modus, die Benutzer über die Tastatur teilen oder Aufteilung eines unterteilten Fensters ermöglichen.

   Dieser Befehl ist deaktiviert, wenn die Sicht nicht in eine Aufteilung ist.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_APP_ABOUT Ruft das Dialogfeld "Info".

   Es ist keine Standardimplementierung für Informationen zu einer Anwendung-Feld. Der Standardwert von AppWizard erstellte Anwendung eine benutzerdefinierten Dialogfeldklasse für Ihre Anwendung erstellt und als Ihre Box zu verwenden. AppWizard wird auch die trivial Befehlshandler schreiben, die mit diesem Befehl verarbeitet und ruft das Dialogfeld.

   Sie können mit diesem Befehl werden fast immer implementieren.

- ID_APP_EXIT Beenden der Anwendung.

   `CWinApp::OnAppExit` verarbeitet mit diesem Befehl, indem Sie eine WM_CLOSE-Meldung an das Hauptfenster der Anwendung senden. Der Standard, das Herunterfahren der Anwendung (und werden aufgefordert, modifizierte Dateien usw.) erfolgt durch die `CFrameWnd` Implementierung.

   Anpassung von diesen Befehlshandler wird nicht empfohlen. Überschreiben von `CWinApp::SaveAllModified` oder `CFrameWnd` schließende Logik wird empfohlen.

   Wenn Sie den Befehl zu implementieren möchten, empfehlen wir, dass es sich bei der Verwendung dieses Befehls-ID.

- ID_HELP_INDEX enthält die Hilfethemen aus. HLP-Datei.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnHelpIndex` mit diesem Befehl behandelt, durch den Aufruf einfach `CWinApp::WinHelp`.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_HELP_USING Zeigt Hilfe zur Verwendung von Hilfe an.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnHelpUsing` mit diesem Befehl behandelt, durch den Aufruf einfach `CWinApp::WinHelp`.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- Modus der ID_CONTEXT_HELP gibt UMSCHALT + F1-Hilfe.

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnContextHelp` verarbeitet mit diesem Befehl, indem Sie den Hilfecursor-Modus festlegen, eine modale Größenanpassungsschleife eingeben, und warten, bis der Benutzer die Auswahl ein Fensters, um Hilfe zu erhalten, auf. Näheres [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für Weitere Informationen zur Implementierung MFC zu unterstützen.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_HELP bietet Hilfe zu den aktuellen Kontext

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   `CWinApp::OnHelp` verarbeitet mit diesem Befehl, indem Sie den richtigen Hilfekontext für den aktuellen Anwendungskontext abrufen. Dadurch wird einfach F1-Hilfe, können in den Meldungsfeldern und so weiter. Näheres [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für Weitere Informationen zu den MFC-Implementierung Hilfe.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_DEFAULT_HELP zeigt standardmäßig die Hilfe für den Kontext

    > [!NOTE]
    >  Sie müssen diese Option, um verbinden Ihrer `CWinApp`-abgeleitete Klasse meldungszuordnung, um diese Funktion zu aktivieren.

   Mit diesem Befehl wird in der Regel zugeordnet `CWinApp::OnHelpIndex`.

   Bei Bedarf eine Unterscheidung zwischen Standardhilfe und im Hilfe-Index ist, kann ein anderen Befehlshandler bereitgestellt werden.

- ID_NEXT_PANE wechselt zum nächsten Bereich

   `CView` verarbeitet diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Ansicht eines unterteilten Fensters gehört, wird mit diesem Befehl an die implementierungsfunktion Delegieren `CSplitterWnd::OnNextPaneCmd`. Dadurch wird die aktive Ansicht zum nächsten Bereich in der Splitter verschoben.

   Dieser Befehl ist deaktiviert, wenn die Ansicht nicht in eine Aufteilung ist, oder es kein Nächster Bereich ist zu wechseln.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_PREV_PANE wechselt zum vorherigen Bereich

   `CView` verarbeitet diesen Befehl für die `CSplitterWnd` Implementierung. Wenn die Ansicht eines unterteilten Fensters gehört, wird mit diesem Befehl an die implementierungsfunktion Delegieren `CSplitterWnd::OnNextPaneCmd`. Dadurch wird die aktive Ansicht zum vorherigen Bereich in der Splitter verschoben.

   Dieser Befehl ist deaktiviert, wenn die Ansicht nicht in eine Aufteilung ist oder keine vorheriger Bereich zu wechseln.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_OLE_INSERT_NEW Fügt ein neues OLE-Objekt

   Zurzeit besteht keine Standardimplementierung für diesen Befehl. Sie müssen diese implementieren Ihrer `CView`-abgeleitete Klasse ein neues OLE-Element/Objekt an der aktuellen Auswahl eingefügt werden soll.

   Alle OLE-Clientanwendungen sollten den Befehl zu implementieren. AppWizard, mit der OLE-Option erstellt eine Skelette-Implementierung der `OnInsertObject` in Ihrer Ansichtsklasse, die Sie ausführen müssen.

   Finden Sie im MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md) Beispiel für eine vollständige Implementierung dieses Befehls.

- ID_OLE_EDIT_LINKS bearbeitet OLE-links

   `COleDocument` verarbeitet mit diesem Befehl mithilfe der bereitgestellten MFC-Implementierung von der standard OLE-Links-Dialog. Die Implementierung dieses Dialogfelds erfolgt über die `COleLinksDialog` Klasse. Wenn das aktuelle Dokument keine Links enthält, wird der Befehl deaktiviert.

   Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_OLE_VERB_FIRST... LETZTE eine ID-Bereich für die OLE-Verben

   `COleDocument` verwendet dieses Befehls-ID-Bereich für die Verben, die von das aktuell ausgewählte OLE-Element/Objekt unterstützt werden. Dies muss ein Bereich sein, da ein bestimmtes Typs des OLE-Item-Objekt auf NULL oder mehr benutzerdefinierte Verben unterstützen kann. Klicken Sie im Menü Ihrer Anwendung sollten Sie ein Menüelement mit der ID des ID_OLE_VERB_FIRST verfügen. Wenn das Programm ausgeführt wird, wird das Menü mit der entsprechenden Verb-Beschreibung (oder ein Popupmenü mit vielen Verben) aktualisiert. Die Verwaltung des OLE-Menüs erfolgt durch `AfxOleSetEditMenu`, Arbeit in der Update-Befehlshandler Benutzeroberfläche für diesen Befehl.

   Es gibt keine explizite Befehlshandler für die Verarbeitung aller die Befehls-ID in diesem Bereich aus. `COleDocument::OnCmdMsg` wird zum Abfangen aller Befehls-IDs in diesem Bereich, in nullbasierte Verb Zahlen zu aktivieren und starten Sie den Server für das jeweilige Verb außer Kraft gesetzt (mit `COleClientItem::DoVerb`).

   Anpassung oder andere Verwendung dieses Befehls-ID-Bereichs wird nicht empfohlen.

- ID_VIEW_TOOLBAR Schaltet die Symbolleiste ein- und ausschalten

   `CFrameWnd` kümmert sich mit diesem Befehl und der Update-Befehlshandler Benutzeroberfläche, um den Sichtbarkeitsstatus der Symbolleiste zu wechseln. Die Symbolleiste muss ein untergeordnetes Fenster des Frames mit untergeordneten Fenster-ID des AFX_IDW_TOOLBAR sein. Die Befehlshandler Schaltet die Sichtbarkeit des Fensters Symbolleiste. `CFrameWnd::RecalcLayout` wird verwendet, das Rahmenfenster, über die Symbolleiste im neuen Zustand neu zu zeichnen. Der Update-Befehls-UI-Handler überprüft das Menüelement, wenn die Symbolleiste sichtbar ist.

   Anpassung von diesen Befehlshandler wird nicht empfohlen. Wenn Sie die zusätzliche Symbolleisten hinzufügen möchten, sollten Sie zu klonen und zu ändern, die den Befehlshandler und die Update-Befehls-UI-Handler für diesen Befehl.

- ID_VIEW_STATUS_BAR Schaltet die Statusleiste ein- und ausschalten

   Mit diesem Befehl wird in implementiert `CFrameWnd` ID_VIEW_TOOLBAR, außer ein anderes untergeordnetes Fenster ID (AFX_IDW_STATUS_BAR) verwendet wird, wie.

## <a name="update-only-command-handlers"></a>Nur-Update-Befehlshandler

Mehrere Standardbefehls-IDs werden als Indikatoren in Statusleisten verwendet. Diese verwenden dasselbe Updatebefehl UI-Mechanismus zur Behandlung, um ihren aktuellen visuellen Zustand während der Leerlaufzeit Anwendung anzuzeigen. Da Sie nicht vom Benutzer ausgewählt werden (d. h. Sie können nicht per Push übertragen einen Statusleistenbereich), und klicken Sie dann nicht sinnvoll, einen ON_COMMAND-Handler für diese Befehls-IDs zu verwenden.

- ID_INDICATOR_CAPS : Indikator der CAP-Sperre.

- ID_INDICATOR_NUM: NUM-Lock-Indikator.

- ID_INDICATOR_SCRL: Kap-Sperrindikator.

- ID_INDICATOR_KANA : KANA Sperren Indikator (gilt nur für japanische Systeme).

Drei davon werden im implementiert `CFrameWnd::OnUpdateKeyIndicator`, eine Implementierung-Hilfe, die die Befehls-ID verwendet, um den entsprechenden virtuellen Schlüssel zuzuordnen. Eine gängige Implementierung aktiviert oder deaktiviert (für Statusbereiche, die deaktiviert = kein Text) der `CCmdUI` Objekt abhängig davon, ob die entsprechende virtuelle Taste derzeit gesperrt ist.

Anpassung von diesen Befehlshandler wird nicht empfohlen.

- ID_INDICATOR_EXT: Indikator für erweiterte Option.

- ID_INDICATOR_OVR : Indikator mit dem Überschreibmodus.

- ID_INDICATOR_REC: Indikator der Aufzeichnung.

Zurzeit besteht keine Standardimplementierung für diese Indikatoren.

Wenn Sie diese Indikatoren implementieren, es wird empfohlen, diesen Indikator IDs und verwalten, die Reihenfolge der Indikatoren in der Statusleiste (d. h. in der folgenden Reihenfolge: EXT, CAP, NUM, SCRL, OVR, REC).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
