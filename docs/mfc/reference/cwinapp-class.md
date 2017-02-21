---
title: "CWinApp Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinApp"
  - "hInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application objects [C++]"
  - "CWinApp class"
  - "HINSTANCE"
  - "main object"
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CWinApp Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse, von der Sie ein Windows\-Anwendungsobjekt berechnen.  
  
## Syntax  
  
```  
class CWinApp : public CWinThread  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinApp::CWinApp](../Topic/CWinApp::CWinApp.md)|Erstellt ein `CWinApp`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)|Fügt eine Normal\-Vorlage der Liste der verfügbaren Dokumentvorlagen hinzu.|  
|[CWinApp::AddToRecentFileList](../Topic/CWinApp::AddToRecentFileList.md)|Fügt einen Dateinamen der zuletzt verwendeten Dateiliste \(MRU\) hinzu.|  
|[CWinApp::ApplicationRecoveryCallback](../Topic/CWinApp::ApplicationRecoveryCallback.md)|Aufgerufen vom Framework wenn wird die Anwendung unerwartet.|  
|[CWinApp::CloseAllDocuments](../Topic/CWinApp::CloseAllDocuments.md)|Alle Dokumente schließen|  
|[CWinApp::CreatePrinterDC](../Topic/CWinApp::CreatePrinterDC.md)|Erstellt einen Druckergerätekontext.|  
|[CWinApp::DelRegTree](../Topic/CWinApp::DelRegTree.md)|Löscht einen angegebenen Schlüssel und alle seine Unterschlüssel.|  
|[CWinApp::DoMessageBox](../Topic/CWinApp::DoMessageBox.md)|implementiert [AfxMessageBox](../Topic/AfxMessageBox.md) für die Anwendung.|  
|[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)|Stellt den Wartecursor an und ab.|  
|[CWinApp::EnableD2DSupport](../Topic/CWinApp::EnableD2DSupport.md)|Ermöglicht Anwendungs\-`D2D`\-Unterstützung.  Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[CWinApp::EnableHtmlHelp](../Topic/CWinApp::EnableHtmlHelp.md)|implementiert HTMLHelp für die Anwendung, anstatt WinHelp.|  
|[CWinApp::EnableTaskbarInteraction](../Topic/CWinApp::EnableTaskbarInteraction.md)|Ermöglicht Taskleisteninteraktion.|  
|[CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)|Überschreiben Sie, um zu bereinigen, wenn die Anwendung beendet wird.|  
|[CWinApp::GetApplicationRecoveryParameter](../Topic/CWinApp::GetApplicationRecoveryParameter.md)|Ruft den Eingabeparameter für die Anwendungswiederherstellungsmethode ab.|  
|[CWinApp::GetApplicationRecoveryPingInterval](../Topic/CWinApp::GetApplicationRecoveryPingInterval.md)|Gibt die Zeitspanne diese die Neustartmanagerwartung die Wiederherstellungsrückruffunktion zurückzukehren zurück.|  
|[CWinApp::GetApplicationRestartFlags](../Topic/CWinApp::GetApplicationRestartFlags.md)|Gibt die Flags für den Neustart\-Manager zurück.|  
|[CWinApp::GetAppRegistryKey](../Topic/CWinApp::GetAppRegistryKey.md)|Rückschrittzeichen für HKEY\_CURRENT\_USER\\"Software"\\RegistryKey\\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](../Topic/CWinApp::GetDataRecoveryHandler.md)|Ruft den Datenwiederherstellungshandler für diese Instanz der Anwendung.|  
|[CWinApp::GetFirstDocTemplatePosition](../Topic/CWinApp::GetFirstDocTemplatePosition.md)|Ruft die Position der ersten Normal\-Vorlage ab.|  
|[CWinApp::GetHelpMode](../Topic/CWinApp::GetHelpMode.md)|Ruft den Typ der Hilfe Verwendung durch die Anwendung ab.|  
|[CWinApp::GetNextDocTemplate](../Topic/CWinApp::GetNextDocTemplate.md)|Ruft die Position einer Normal\-Vorlage ab.  Kann rekursiv verwendet werden.|  
|[CWinApp::GetPrinterDeviceDefaults](../Topic/CWinApp::GetPrinterDeviceDefaults.md)|Ruft die Druckergerätenstandards ab.|  
|[CWinApp::GetProfileBinary](../Topic/CWinApp::GetProfileBinary.md)|Ruft Binärdaten aus einem Eintrag in der INI\-Datei der Anwendung ab.|  
|[CWinApp::GetProfileInt](../Topic/CWinApp::GetProfileInt.md)|Ruft eine ganze Zahl aus einem Eintrag in der INI\-Datei der Anwendung ab.|  
|[CWinApp::GetProfileString](../Topic/CWinApp::GetProfileString.md)|Ruft eine Zeichenfolge mit einem Eintrag in der INI\-Datei der Anwendung ab.|  
|[CWinApp::GetSectionKey](../Topic/CWinApp::GetSectionKey.md)|Rückschrittzeichen für HKEY\_CURRENT\_USER\\"Software"\\RegistryKey\\AppName\\lpszSection.|  
|[CWinApp::HideApplication](../Topic/CWinApp::HideApplication.md)|vor dem Schließen aller Dokumente blendet die Anwendung aus.|  
|[CWinApp::HtmlHelp](../Topic/CWinApp::HtmlHelp.md)|Ruft die `HTMLHelp` Windows\-Funktion auf.|  
|[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)|Überschreiben Sie, um von Windows\-Instanzinitialisierung, wie das Erstellen der Fensterobjekte auszuführen.|  
|[CWinApp::IsTaskbarInteractionEnabled](../Topic/CWinApp::IsTaskbarInteractionEnabled.md)|Teilt mit, ob Windows 7\-Taskleisteninteraktion aktiviert ist.|  
|[CWinApp::LoadCursor](../Topic/CWinApp::LoadCursor.md)|Lädt eine Cursorressource.|  
|[CWinApp::LoadIcon](../Topic/CWinApp::LoadIcon.md)|Lädt eine Symbolressource.|  
|[CWinApp::LoadOEMCursor](../Topic/CWinApp::LoadOEMCursor.md)|Lädt einen vordefinierten Cursor Windows OEM, den die **OCR\_** Konstanten in WINDOWS.H. angeben.|  
|[CWinApp::LoadOEMIcon](../Topic/CWinApp::LoadOEMIcon.md)|Lädt ein vordefiniertes Symbol Windows OEM, das die **OIC\_** Konstanten in WINDOWS.H. angeben.|  
|[CWinApp::LoadStandardCursor](../Topic/CWinApp::LoadStandardCursor.md)|Lädt einen Windows vordefinierten Cursor, den die **IDC\_** Konstanten in WINDOWS.H. angeben.|  
|[CWinApp::LoadStandardIcon](../Topic/CWinApp::LoadStandardIcon.md)|Lädt ein Windows vordefiniertes Symbol, das die **IDI\_** Konstanten in WINDOWS.H. angeben.|  
|[CWinApp::OnDDECommand](../Topic/CWinApp::OnDDECommand.md)|Aufgerufen vom Framework als Reaktion auf einen dynamischen Datenaustausch \(DDE\) führen Sie Befehl aus.|  
|[CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md)|Überschreiben Sie, um den anwendungsspezifischen Leerlaufverarbeitens auszuführen.|  
|[CWinApp::OpenDocumentFile](../Topic/CWinApp::OpenDocumentFile.md)|Aufgerufen vom Framework, um ein Dokument aus einer Datei zu öffnen.|  
|[CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)|Analysiert einzelne Parameter und Flags in der Befehlszeile.|  
|[CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md)|Filtert Meldungen, bevor sie an den Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) weitergeleitet werden.|  
|[CWinApp::ProcessMessageFilter](../Topic/CWinApp::ProcessMessageFilter.md)|Abfangbestimmte Meldungen, bevor die Anwendung erreichen.|  
|[CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)|Behandelt Befehlszeilenargumente und \-Flags.|  
|[CWinApp::ProcessWndProcException](../Topic/CWinApp::ProcessWndProcException.md)|Fängt alle Ausnahmen ab, die von der der Meldung und von den Befehlshandlern Anwendung ausgelöst werden.|  
|[CWinApp::Register](../Topic/CWinApp::Register.md)|Performs passte Registrierung an.|  
|[CWinApp::RegisterWithRestartManager](../Topic/CWinApp::RegisterWithRestartManager.md)|Registriert die Anwendung mit dem Neustart\-Manager.|  
|[CWinApp::ReopenPreviousFilesAtRestart](../Topic/CWinApp::ReopenPreviousFilesAtRestart.md)|Bestimmt, ob der Neustart\-Manager die Dateien erneut öffnet, die geöffnet waren, als die Anwendung unerwartet beendet wurde.|  
|[CWinApp::RestartInstance](../Topic/CWinApp::RestartInstance.md)|Behandelt einen Anwendungsneustart, der vom Neustart\-Manager initiiert wird.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](../Topic/CWinApp::RestoreAutosavedFilesAtRestart.md)|Bestimmt, ob der Neustart\-Manager die automatisch gespeicherten Dateien wiederhergestellt werden, wenn die Anwendung neu gestartet.|  
|[CWinApp::Run](../Topic/CWinApp::Run.md)|Führt die standardmäßige Meldungsschleife aus.  Überschreiben Sie, um die Meldungsschleife anzupassen.|  
|[CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)|Testet die Befehlszeile der Anwendung für die **\/Automation** Option.  Veraltet.  Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md), nachdem Sie [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md) aufgerufen haben.|  
|[CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)|Testet die Befehlszeile der Anwendung für die **\/Embedding** Option.  Veraltet.  Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md), nachdem Sie [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md) aufgerufen haben.|  
|[CWinApp::SaveAllModified](../Topic/CWinApp::SaveAllModified.md)|Fordert den Benutzer auf, alle geänderten Dokumente zu speichern.|  
|[CWinApp::SelectPrinter](../Topic/CWinApp::SelectPrinter.md)|Wählt einen Drucker aus, der zuvor von einem Benutzer durch ein Dialogfeld Drucken angegeben wird.|  
|[CWinApp::SetHelpMode](../Topic/CWinApp::SetHelpMode.md)|Sätze und initialisiert den Typ der Hilfe Verwendung durch die Anwendung.|  
|[CWinApp::SupportsApplicationRecovery](../Topic/CWinApp::SupportsApplicationRecovery.md)|Bestimmt, ob der Neustart\-Manager eine Anwendung wiederhergestellt, die unerwartet beendet wurde.|  
|[CWinApp::SupportsAutosaveAtInterval](../Topic/CWinApp::SupportsAutosaveAtInterval.md)|Bestimmt, ob der Neustart\-Manager geöffnete Dokumente in regelmäßigen Intervallen automatisch speichert.|  
|[CWinApp::SupportsAutosaveAtRestart](../Topic/CWinApp::SupportsAutosaveAtRestart.md)|Bestimmt, ob der Neustart\-Manager alle geöffneten Dokumente wenn die Anwendungsneustarts automatisch speichert.|  
|[CWinApp::SupportsRestartManager](../Topic/CWinApp::SupportsRestartManager.md)|Bestimmt, ob die Anwendung den Neustart\-Manager unterstützt.|  
|[CWinApp::Unregister](../Topic/CWinApp::Unregister.md)|Hebt die Registrierung aller bezeichnet wird, durch das `CWinApp`\-Objekt registriert werden.|  
|[CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)|Ruft die `WinHelp` Windows\-Funktion auf.|  
|[CWinApp::WriteProfileBinary](../Topic/CWinApp::WriteProfileBinary.md)|Schreibt Binärdaten einem Eintrag in der INI\-Datei der Anwendung.|  
|[CWinApp::WriteProfileInt](../Topic/CWinApp::WriteProfileInt.md)|Schreibt eine ganze Zahl einem Eintrag in der INI\-Datei der Anwendung.|  
|[CWinApp::WriteProfileString](../Topic/CWinApp::WriteProfileString.md)|Schreibt eine Zeichenfolge in einen Eintrag in der INI\-Datei der Anwendung.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)|Ermöglicht den Benutzern das Öffnen von Datendateien vom Windows\-Datei\-Manager.|  
|[CWinApp::LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)|Lädt Standardini\-datei\-Einstellungen und ermöglicht die MRU\-Dateilistenfunktion.|  
|[CWinApp::OnContextHelp](../Topic/CWinApp::OnContextHelp.md)|Handles UMSCHALT\+F1\-Hilfe innerhalb der Anwendung.|  
|[CWinApp::OnFileNew](../Topic/CWinApp::OnFileNew.md)|Implementiert den `ID_FILE_NEW` Befehl.|  
|[CWinApp::OnFileOpen](../Topic/CWinApp::OnFileOpen.md)|Implementiert den `ID_FILE_OPEN` Befehl.|  
|[CWinApp::OnFilePrintSetup](../Topic/CWinApp::OnFilePrintSetup.md)|Implementiert den `ID_FILE_PRINT_SETUP` Befehl.|  
|[CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)|Handle\-F1\-Hilfe innerhalb der Anwendung \(mithilfe der aktuelle Kontext\).|  
|[CWinApp::OnHelpFinder](../Topic/CWinApp::OnHelpFinder.md)|Behandelt die `ID_HELP_FINDER` und `ID_DEFAULT_HELP` Befehle.|  
|[CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)|Behandelt den `ID_HELP_INDEX` Befehl und stellt ein standardmäßiges Hilfethema bereit.|  
|[CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)|Behandelt den Befehl `ID_HELP_USING`.|  
|[CWinApp::RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md)|Registriert Dokumenttypen der Anwendung mit dem Windows\-Datei\-Manager.|  
|[CWinApp::SetAppID](../Topic/CWinApp::SetAppID.md)|Legt Anwendungs\-Benutzer\-Modell\-ID explizit für die Anwendung fest.  Diese Methode sollte aufgerufen werden, bevor jede Benutzeroberfläche Benutzer angezeigt wird \(der beste Ort ist der Anwendungskonstruktor\).|  
|[CWinApp::SetRegistryKey](../Topic/CWinApp::SetRegistryKey.md)|Veranlasst Anwendungseinstellungen, in der Registrierung anstelle INI\-Dateien gespeichert.|  
|[CWinApp::UnregisterShellFileTypes](../Topic/CWinApp::UnregisterShellFileTypes.md)|Hebt Dokumenttypen der Anwendung mit dem Windows\-Datei\-Manager Registrierung auf.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CWinApp::m\_bHelpMode](../Topic/CWinApp::m_bHelpMode.md)|Gibt an, wenn der Benutzer im Hilfekontextmodus ist \(in der Regel aufgerufen mit UMSCHALT\+F1\).|  
|[CWinApp::m\_eHelpType](../Topic/CWinApp::m_eHelpType.md)|Gibt den Typ der Hilfe Verwendung durch die Anwendung an.|  
|[CWinApp::m\_hInstance](../Topic/CWinApp::m_hInstance.md)|Identifiziert die aktuelle Instanz der Anwendung.|  
|[CWinApp::m\_lpCmdLine](../Topic/CWinApp::m_lpCmdLine.md)|Zeigt auf eine auf NULL endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt.|  
|[CWinApp::m\_nCmdShow](../Topic/CWinApp::m_nCmdShow.md)|Gibt an, wie das Fenster zuerst angezeigt werden soll.|  
|[CWinApp::m\_pActiveWnd](../Topic/CWinApp::m_pActiveWnd.md)|Zeiger auf das Hauptfenster der Containeranwendung, wenn ein OLE\-Server direkt aktiviert ist.|  
|[CWinApp::m\_pszAppID](../Topic/CWinApp::m_pszAppID.md)|Anwendungs\-Benutzer\-Modell ID|  
|[CWinApp::m\_pszAppName](../Topic/CWinApp::m_pszAppName.md)|Gibt den Namen der Anwendung an.|  
|[CWinApp::m\_pszExeName](../Topic/CWinApp::m_pszExeName.md)|Der Modulname der Anwendung.|  
|[CWinApp::m\_pszHelpFilePath](../Topic/CWinApp::m_pszHelpFilePath.md)|Der Pfad zur Hilfedatei der Anwendung.|  
|[CWinApp::m\_pszProfileName](../Topic/CWinApp::m_pszProfileName.md)|Der INI\-Dateiname der Anwendung.|  
|[CWinApp::m\_pszRegistryKey](../Topic/CWinApp::m_pszRegistryKey.md)|Wird verwendet, um den vollständigen Registrierungsschlüssel zum Speichern von Anwendungsprofileinstellungen zu bestimmen.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)|Flags, die bestimmen, wie der Neustart\-Manager verhält.|  
|[CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)|Die Zeit in Millisekunden zwischen speichert automatisch.|  
|[CWinApp::m\_pDataRecoveryHandler](../Topic/CWinApp::m_pDataRecoveryHandler.md)|Zeiger auf Datenwiederherstellungshandler für die Anwendung.|  
  
## Hinweise  
 Ein Anwendungsobjekt enthält Memberfunktionen für das Initialisieren der Anwendung \(und jeder Instanz davon\) und zum Ausführen der Anwendung.  
  
 Jede Anwendung, die die Microsoft Foundations\-Klassen verwendet, kann ein Objekt nur enthalten, das von `CWinApp` abgeleitet wird.  Dieses Objekt wird erstellt, wenn andere globale Objekte C\+\+ erstellt werden und ist bereits verfügbar, wenn Windows die `WinMain`\-Funktion aufruft, die von Microsoft Foundation Class\-Bibliothek angegeben wird.  Deklarieren Sie das `CWinApp` abgeleitetes Objekt auf globaler Ebene.  
  
 Wenn Sie eine Anwendungsklasse von `CWinApp` ableiten, überschreiben Sie die [InitInstance](../Topic/CWinApp::InitInstance.md)\-Memberfunktion, um Hauptfensterobjekt Ihrer Anwendung erstellen.  
  
 Zusätzlich zu den `CWinApp`\-Memberfunktionen stellt Microsoft Foundation Class\-Bibliothek die folgenden globalen Funktionen, um das `CWinApp`\-Objekt und auf andere globale Informationen zugreifen:  
  
-   [AfxGetApp](../Topic/AfxGetApp.md) wird ein Zeiger auf `CWinApp`\-Objekt.  
  
-   [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) erhält ein Handle zur aktuellen Anwendungsinstanz.  
  
-   [AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md) erhält ein Handle für die Ressourcen der Anwendung.  
  
-   [AfxGetAppName](../Topic/AfxGetAppName.md) wird ein Zeiger auf eine Zeichenfolge, die den Namen der Anwendung enthält.  Alternativ wenn Sie einen Zeiger auf das Objekt `CWinApp` haben, verwenden Sie `m_pszExeName`, den Namen der Anwendung abzurufen.  
  
 Siehe [CWinApp: Die Application\-Klasse](../../mfc/cwinapp-the-application-class.md) für mehr auf der `CWinApp`\-Klasse, einschließlich eine Übersicht der folgenden:  
  
-   `CWinApp` von abgeleiteten Code vom Anwendungs\-Assistenten geschrieben.  
  
-   Die Rolle von `CWinApp` in der Ausführungssequenz der Anwendung.  
  
-   Die Standardmemberfunktionsimplementierungen von `CWinApp`.  
  
-   Die wichtigsten überschreibbaren Elemente von `CWinApp`.  
  
 Der **m\_hPrevInstance** Datenmember nicht mehr vorhanden ist.  Informationen zum Erkennen einer vorherigen Instanz von `CWinApp`, finden Sie im Knowledge Base\-Artikel "wie eine vorherige Instanz einer Anwendung" \(KB106385\) an [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;106385](http://support.microsoft.com/default.aspx?scid=kb;en-us;106385) identifiziert.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CWinThread Class](../../mfc/reference/cwinthread-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Gewusst wie: Hinzufügen von Unterstützung für den Neustart\-Manager](../../mfc/how-to-add-restart-manager-support.md)