---
title: Spezielle CWinApp-Dienste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8734bfd4e673e1298d6822bbd272e2d70ff7a81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="special-cwinapp-services"></a>Spezielle CWinApp-Dienste
Neben die Nachrichtenschleife ausführen und und Sie haben die Gelegenheit, die Anwendung zu initialisieren und bereinigen, [CWinApp](../mfc/reference/cwinapp-class.md) mehrere andere Dienste bereitstellt.  
  
##  <a name="_core_shell_registration"></a>Shell-Registrierung  
 Standardmäßig ermöglicht der Anwendung MFC-Assistent für den Benutzer zum Öffnen von Datendateien, die Ihre Anwendung durch Doppelklicken in der Datei-Explorer oder Datei-Manager erstellt wurden. Wenn die Anwendung eine MDI-Anwendung ist, und geben Sie eine Erweiterung für die Dateien die Anwendung erstellt, fügt der MFC-Anwendung-Assistent Aufrufe an die [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) und [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)Memberfunktionen der [CWinApp](../mfc/reference/cwinapp-class.md) auf die `InitInstance` überschreiben, die für Sie geschrieben.  
  
 `RegisterShellFileTypes`registriert die Anwendung Dokumenttypen mit Datei-Explorer oder Datei-Manager. Die Funktion hinzugefügt der Registration-Datenbank, die zur Verwaltung von Windows Einträge. Die Einträge registrieren jeden Dokumenttyp, der Dateityp Erweiterung zuordnen, geben Sie eine Befehlszeile, um die Anwendung zu öffnen und geben Sie einen Befehl für dynamischen Datenaustausch (DDE), ein Dokument dieses Typs öffnen.  
  
 `EnableShellOpen`Schließt den Prozess Ihrer Anwendung DDE-Befehle aus dem Datei-Explorer oder Datei-Manager zum Öffnen der Datei, die vom Benutzer ausgewählten empfangen können.  
  
 Diese Unterstützung für die automatische Registrierung in `CWinApp` entfällt die Notwendigkeit eine REG-Datei mit Ihrer Anwendung zu senden oder zu besondere Installationsarbeit zu erledigen.  
  
 Initialisieren von GDI + für Ihre Anwendung verwendet werden sollen (durch Aufrufen von [GdiplusStartup]--Brokenlink--(_Gdiplus_FUNC_GdiplusStartup_token_input_output_) in Ihrer [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Funktion), müssen Sie GDI +-Hintergrundthread zu unterdrücken.  
  
 Hierzu können Sie durch Festlegen der **SuppressBackgroundThread** Mitglied der [GdiplusStartupInput]--brokenlink--(_gdiplus_STRUC_GdiplusStartupInput)-Struktur, um **"true"**. Wenn Unterdrücken von GDI + Hintergrundthread, der **NotificationHook** und **NotificationUnhook** aufrufen (Siehe [GdiplusStartupOutput]--brokenlink--(_gdiplus_STRUC_GdiplusStartupOutput)) sollten unmittelbar vor dem eingeben, und beenden die Anwendung die Meldungsschleife vorgenommen Sie werden. Aus diesem Grund ist eine gute Aufrufen **GdiplusStartup** und die Benachrichtigung Hookfunktionen wäre in einer Überschreibung der virtuellen Funktion [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run), wie unten dargestellt:  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 Wenn Sie den Hintergrund GDI +-Thread nicht unterdrücken, können DDE-Befehle an die Anwendung vorzeitig ausgestellt werden, bevor das Hauptfenster erstellt wurde. Die DDE-Befehle, die von der Shell können Fehlermeldungen resultierende vorzeitig abgebrochen werden.  
  
##  <a name="_core_file_manager_drag_and_drop"></a>Manager für Dateiserver Drag & Drop  
 Dateien können in einem Fenster in der Anwendung aus dem Dateiansichtsfenster im Datei-Manager oder Datei-Explorer gezogen werden. Sie können z. B. eine oder mehrere Dateien auf eine MDI-Anwendung Hauptfenster gezogen werden, in dem die Anwendung die Dateinamen abrufen konnte, und öffnen Sie untergeordnete MDI-Fenster für diese Dateien aktivieren.  
  
 Zum Aktivieren Datei Drag und drop in Ihrer Anwendung, schreibt der MFC-Anwendung-Assistent einen Aufruf der [CWnd](../mfc/reference/cwnd-class.md) Memberfunktion [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) für das Hauptrahmenfenster in Ihre `InitInstance`. Sie können diesen Aufruf entfernen, wenn Sie nicht, um den Drag & Drop-Funktion zu implementieren möchten.  
  
> [!NOTE]
>  Sie können auch weitere allgemeine Drag-and-Drop-Funktionen implementieren – Ziehen von Daten zwischen oder innerhalb von Dokumenten – mit OLE. Informationen finden Sie im Artikel [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a>Nachverfolgen der am meisten zuletzt verwendete Dokumente  
 Der Benutzer öffnet und schließt Dateien, der nachverfolgt das Anwendungsobjekt die vier zuletzt verwendeten Dateien. Die Namen dieser Dateien sind im Menü Datei hinzugefügt und aktualisiert, wenn sich diese ändern. Das Framework speichert diese Dateinamen in der Registrierung oder in der INI-Datei mit dem gleichen Namen wie das Projekt und aus der Datei gelesen, wenn die Anwendung wird gestartet. Die `InitInstance` außer Kraft gesetzt, die MFC-Anwendungs-Assistent erstellt, Sie enthält einen Aufruf von der [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), lädt die Informationen aus der Registrierung oder der INI- Datei, einschließlich der zuletzt verwendeten Dateinamen.  
  
 Diese Einträge werden wie folgt gespeichert:  
  
-   In Windows NT, Windows 2000 und höher, wird der Wert an einem Registrierungsschlüssel gespeichert.  
  
-   In Windows 3.x, den Wert in der WIN gespeichert ist. INI-Datei.  
  
-   In Windows 95 und höher wird der Wert in eine zwischengespeicherte Version der WIN gespeichert. INI.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)