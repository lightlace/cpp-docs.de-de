---
title: Spezielle CWinApp-Dienste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79d3744b5accf9b1ab45f6881afb4683dfc967fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431521"
---
# <a name="special-cwinapp-services"></a>Spezielle CWinApp-Dienste

Neben dem die Meldungsschleife ausführt, und bietet Ihnen die Möglichkeit, initialisieren Sie die Anwendung aus, und bereinigen Sie nach, [CWinApp](../mfc/reference/cwinapp-class.md) mehrere andere Dienste bereitstellt.

##  <a name="_core_shell_registration"></a> Shell-Registrierung

Standardmäßig ermöglicht der MFC-Anwendung-Assistent für den Benutzer zum Öffnen von Datendateien, die Ihre Anwendung durch Doppelklicken in Datei-Explorer oder Datei-Manager erstellt wurden. Wenn Ihre Anwendung eine MDI-Anwendung ist, und geben Sie eine Erweiterung für die Dateien der Anwendung erstellt, fügt die MFS-Anwendungsassistenten Aufrufe an die [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) und [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)Memberfunktionen der [CWinApp](../mfc/reference/cwinapp-class.md) auf die `InitInstance` außer Kraft setzen, die es für Sie schreibt.

`RegisterShellFileTypes` Datei-Explorer oder Datei-Manager registriert Dokumenttypen Ihrer Anwendung. Die Funktion hinzugefügt der Registrierungsdatenbank, in der Windows verwaltet Einträge. Die Einträge registrieren jeden Dokumenttyp, den Dateityp eine Dateierweiterung zuordnen, geben Sie eine Befehlszeile zum Öffnen der Anwendung und geben Sie einen dynamischen Datenaustausch (DDE) Befehl, ein Dokument dieses Typs öffnen.

`EnableShellOpen` Schließt den Prozess durch, sodass Ihre Anwendung zum Empfangen von DDE-Befehle von Datei-Explorer oder Datei-Manager, um die vom Benutzer ausgewählten Datei öffnen.

Diese Unterstützung der automatischen Registrierung in `CWinApp` entfällt die Notwendigkeit eine REG-Datei mit Ihrer Anwendung zu senden oder eine besondere Installation Aktion auszuführen.

Wenn GDI + für Ihre Anwendung nicht initialisiert werden sollen (durch Aufrufen von [GdiplusStartup](/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) in Ihre [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Funktion), müssen Sie die GDI +-Hintergrundthread zu unterdrücken.

Sie erreichen dies durch Festlegen der `SuppressBackgroundThread` Mitglied der [GdiplusStartupInput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) -Struktur in **"true"**. Wenn Unterdrücken von GDI +-Thread im Hintergrund die `NotificationHook` und `NotificationUnhook` sollte aufgerufen werden nur vor betreten und beendet die Nachrichtenschleife der Anwendung wird. Weitere Informationen zu diesen aufrufen, finden Sie unter [GdiplusStartupOutput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput). Aus diesem Grund eine gute Möglichkeit zum Aufrufen `GdiplusStartup` und die Hookfunktionen für die Benachrichtigung in einer Überschreibung der virtuellen Funktion wäre [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run), wie unten dargestellt:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Wenn Sie den Hintergrund GDI +-Thread nicht unterdrücken, können DDE-Befehle an die Anwendung vorzeitig ausgestellt werden, bevor das Hauptfenster erstellt wurde. Die DDE-Befehle, die von der Shell ausgegeben können führt Fehlermeldungen vorzeitig abgebrochen werden.

##  <a name="_core_file_manager_drag_and_drop"></a> Manager für Dateiserver Drag & Drop

Dateien können in einem Fenster in Ihrer Anwendung aus dem Fenster Datei anzeigen, in dem Datei-Manager oder Datei-Explorer gezogen werden. Sie können z. B. eine oder mehrere Dateien zum Hauptfenster für eine MDI-Anwendung, gezogen werden, dem die Anwendung rufen Sie die Dateinamen und Öffnen von untergeordneten MDI-Fenster für diese Dateien kann aktivieren.

Zur Aktivierung der Datei Drag & drop in Ihrer Anwendung, schreibt die MFS-Anwendungsassistenten einen Aufruf der [CWnd](../mfc/reference/cwnd-class.md) Memberfunktion [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) für das Hauptrahmenfenster in Ihre `InitInstance`. Sie können diesen Aufruf entfernen, wenn Sie nicht, für die Implementierung der Drag & Drop-Funktion möchten.

> [!NOTE]
>  Sie können auch weitere allgemeine Drag & Drop-Funktionen implementieren: Ziehen von Daten zwischen oder innerhalb von Dokumenten – mit OLE. Informationen finden Sie im Artikel [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md).

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Nachverfolgen der am häufigsten zuletzt verwendete Dokumente

Da der Benutzer öffnet und Dateien schließt, verfolgt des das Anwendungsobjekt der vier zuletzt verwendeten Dateien. Die Namen dieser Dateien sind im Menü Datei hinzugefügt und aktualisiert, wenn sie ändern. Das Framework speichert diesen Dateinamen aus, in der Registrierung oder in der Initialisierungsdatei mit dem gleichen Namen wie Ihr Projekt, und liest diese aus der Datei ein, wenn die Anwendung wird gestartet. Die `InitInstance` außer Kraft setzen, dass die MFC-Anwendungs-Assistent erstellt, für Sie einen Aufruf enthält der [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), lädt die Informationen, aus der Registrierung oder der INI- -Datei, einschließlich der zuletzt verwendeten Dateinamen.

Diese Einträge werden wie folgt gespeichert:

- In Windows NT, Windows 2000 und höher, wird der Wert auf einen Registrierungsschlüssel gespeichert.

- In Windows 3.x, der Wert befindet sich in der Windows-Taste. INI-Datei.

- In Windows 95 und höher wird der Wert in eine zwischengespeicherte Version des Windows-Taste gespeichert. INI.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)