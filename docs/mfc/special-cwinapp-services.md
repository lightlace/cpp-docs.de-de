---
title: "Spezielle CWinApp-Dienste | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadStdProfileSettings"
  - "EnableShellOpen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsobjekte [C++], Dienste"
  - "CWinApp-Klasse, Drag & Drop (Datei-Manager)"
  - "CWinApp-Klasse, Initialisieren von GDI+"
  - "CWinApp-Klasse, zuletzt verwendete Dokumente"
  - "CWinApp-Klasse, Dienste"
  - "CWinApp-Klasse, Shell-Registrierung"
  - "Drag & Drop [C++], Dateien"
  - "DragAcceptFiles-Methode"
  - "EnableShellOpen-Methode"
  - "Dateien [C++], Drag & Drop"
  - "Dateien [C++], zuletzt verwendet"
  - "GDI+, Initialisierung für MFC"
  - "GDI+, Unterdrücken des Hintergrundthreads [MFC]"
  - "LoadStdProfileSettings-Methode"
  - "MFC [C++], Dateivorgänge"
  - "MFC [C++], Liste der zuletzt verwendeten Dateien"
  - "MFC [C++], Shell-Registrierung"
  - "MRU-Listen"
  - "Registrierung von Dateitypen"
  - "RegisterShellFileTypes-Methode"
  - "Registrierung [C++], Shell"
  - "Registrierung [C++], Zuletzt verwendete Dateien"
  - "Dienste, von CWinApp bereitgestellt"
  - "Shell, Registrierung von Dateitypen"
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Spezielle CWinApp-Dienste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Neben dem Ausführen der Nachrichtenschleife und dem Geben Sie eine Möglichkeit, die Anwendung zu initialisieren und nach Umgebung zu bereinigen, stellt [CWinApp](../mfc/reference/cwinapp-class.md) mehrere andere Dienste.  
  
##  <a name="_core_shell_registration"></a> Shell\-Registrierung  
 Standardmäßig macht der MFC\-Anwendungs\-Assistent es möglich, dass der Benutzer Datendateien öffnet, die Anwendung erstellt wurde, indem Sie im Datei\-Explorer oder im Datei\-Manager doppelt geklickt hat.  Wenn die Anwendung eine MDI\-Anwendung ist und Sie eine Erweiterung für die Dateien angeben, die die Anwendung erstellt, fügt der MFC\-Anwendungs\-Assistent Aufrufe [RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md) hinzu und [EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)\-Memberfunktionen von [CWinApp](../mfc/reference/cwinapp-class.md) zu `InitInstance` überschreiben, damit es für Sie.  
  
 `RegisterShellFileTypes` registriert die Dokumenttypen der Anwendung mit Datei\-Explorer oder Datei\-Manager.  Die Funktion werden dem der Registrierungsdatenbank hinzu, die Windows beibehält.  Die Einträge registrieren jeden Dokumenttyp, ordnen eine Dateierweiterung mit dem Dateityp zu, geben eine Befehlszeile an, um die Anwendung zu öffnen und ein Befehl \(DDE\)\- des dynamischen Datenaustauschs an, ein Dokument dieses Typs zu öffnen.  
  
 `EnableShellOpen` enthält den Prozess ab, indem es ermöglicht, eine Anwendung DDE\-Befehle Explorer oder Datei\-Manager von Datei zu erhalten, die Datei öffnen, die vom Benutzer ausgewählt wird.  
  
 Diese automatische Registrierungsunterstützung in `CWinApp` entfällt die Notwendigkeit, eine REG\-Datei mit der Anwendung erfordert oder Sondereinbauarbeit erledigt.  
  
 GDI\+ Wenn Sie für die Anwendung initialisiert werden sollen \(durch Aufrufen von [GdiplusStartup](_gdiplus_FUNC_GdiplusStartup_token_input_output_) in der [InitInstance](../Topic/CWinApp::InitInstance.md)\-Funktion\), müssen Sie den GDI\+\-Hintergrundthread unterdrücken.  
  
 Sie erreichen dies, indem Sie dem **SuppressBackgroundThread**\-Member der Struktur [GdiplusStartupInput](_gdiplus_STRUC_GdiplusStartupInput) auf **TRUE** festlegen.  Wenn Sie den GDI\+\-Hintergrundthread unterdrückt, sollten **NotificationHook** und die **NotificationUnhook** \- Aufrufe \(siehe [GdiplusStartupOutput](_gdiplus_STRUC_GdiplusStartupOutput)\), nur vor dem Eingeben und beenden der Meldungsschleife der Anwendung aufgerufen werden.  Deshalb wäre ein gut, um von **GdiplusStartup** aufzurufen und die Hookbenachrichtigungsfunktionen in einer Überschreibung der virtuellen Funktion [CWinApp::Run](../Topic/CWinApp::Run.md), wie unten sein:  
  
 [!CODE [NVC_MFCDocView#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#6)]  
  
 Wenn der Hintergrund GDI\+\-Thread unterdrücken, können DDE\-Befehle zur Anwendung vorzeitig ausgegeben werden, bevor sein Hauptfenster erstellt wurde.  Die DDE\-Befehle, die von der Shell, ausgegeben werden können, d Fehlermeldungen vorzeitig abgebrochen werden.  
  
##  <a name="_core_file_manager_drag_and_drop"></a> Datei\-Manager\-Drag & Drop  
 Dateien können im Dateiansichtsfenster im Datei\-Manager oder im Datei\-Explorer zu einem Fenster in der Anwendung gezogen werden.  Sie haben beispielsweise mindestens eine an das Hauptfenster zu ziehende Dateien, einer MDI\-Anwendung, in dem die Anwendung die Dateinamen abrufen und untergeordnete MDI\-Fenster für diese Dateien öffnen kann.  
  
 Um Datei\-Drag& Drop in Ihrer Anwendung aktivieren können, erstellt der MFC\-Anwendungs\-Assistent einen Aufruf der Memberfunktion [CWnd](../mfc/reference/cwnd-class.md)[DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md) für das Hauptrahmenfenster im `InitInstance`.  Sie können diesen Aufruf entfernen, wenn die Drag & Drop\-Funktion implementieren möchten.  
  
> [!NOTE]
>  Sie können Drag allgemeineren & Drop implementieren auch Daten Dokument\-mit OLE zwischen oder darin Funktion\-ziehend.  Weitere Informationen finden Sie im Artikel [Drag & Drop \(OLE\)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Verfolgen der zuletzt verwendeten Dokumente  
 Wenn der Benutzer Dateien öffnet und schließt, verwaltet das Anwendungsobjekt die vier zuletzt verwendeten Dateien nachverfolgt.  Die Namen dieser Dateien werden zur Menü hinzugefügt und aktualisiert, wenn sie ändern.  Das Framework speichert diese Dateinamen entweder in der Registrierung oder in der INI\-Datei, mit dem gleichen Namen wie das Projekt und liest sie aus der Datei, wenn die Anwendung startet oben.  Die `InitInstance`, die Überschreibung der MFC\-Anwendungs\-Assistent für Sie erstellt, enthält einen Aufruf der Memberfunktion [CWinApp](../mfc/reference/cwinapp-class.md)[LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md), die Informationen aus der Registrierung oder der INI\-Datei lädt, einschließlich die zuletzt verwendeten Dateinamen.  
  
 Diese Einträge gespeichert werden, wie folgt:  
  
-   In Windows NT wird Windows 2000 und höher, der Wert in einen Registrierungsschlüssel gespeichert.  
  
-   In Windows 3.x, wird der Wert in der WIN.INI\-Datei gespeichert.  
  
-   In Windows 95 und höher, wird der Wert in eine zwischengespeicherte Version von WIN.INI gespeichert.  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)