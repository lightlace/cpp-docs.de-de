---
title: CWinApp-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
dev_langs: C++
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99e773dc7c5039574901c2a13433615f8a0c0aad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cwinapp-class"></a>CWinApp-Klasse
Die Basisklasse, von der ein Windows-Anwendungsobjekt abgeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|Erstellt ein `CWinApp`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp:: AddDocTemplate](#adddoctemplate)|Fügt eine Dokumentvorlage Liste der verfügbaren Dokumentvorlagen in der Anwendung an.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Fügt einen Dateinamen an die zuletzt verwendeten Dateiliste (MRU).|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|Schließt alle geöffneten Dokumente.|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|Erstellt einen Drucker-Gerätekontext.|  
|[CWinApp::DelRegTree](#delregtree)|Löscht einen angegebenen Schlüssel und alle seine Unterschlüssel.|  
|[CWinApp::DoMessageBox](#domessagebox)|Implementiert [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) für die Anwendung.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|Schaltet den Wartecursor ein und aus.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Ermöglicht der Anwendung `D2D` unterstützen. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Die Anwendung, anstatt WinHelp HTMLHelp implementiert.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Ermöglicht die Interaktion der Taskleiste.|  
|[CWinApp:: ExitInstance](#exitinstance)|Außer Kraft setzen Sie, um zu bereinigen, wenn die Anwendung beendet wird.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Ruft die Eingabeparameter für die Anwendung Wiederherstellungsmethode ab.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Gibt die Zeitdauer, die der Neustart-Manager wartet, bis die Wiederherstellung Rückruffunktion zurückgegeben.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Gibt die Flags für den Neustart-Manager zurück.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Gibt Schlüssel HKEY_CURRENT_USER\\\RegistryKey\ProfileName "Software".|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Ruft den Datenhandler für die Wiederherstellung für diese Instanz der Anwendung ab.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Ruft die Position des ersten Dokumentvorlage ab.|  
|[CWinApp::GetHelpMode](#gethelpmode)|Ruft den Typ der Hilfe verwendet, die von der Anwendung ab.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Ruft die Position des eine Dokumentvorlage ab. Rekursiv verwendet kann werden.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Ruft die Standardwerte der Drucker Gerät ab.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|Ruft die Binärdaten aus einem Eintrag in der Anwendungsverzeichnis ab. INI-Datei.|  
|[CWinApp::GetProfileInt](#getprofileint)|Ruft eine ganze Zahl aus einem Eintrag in der Anwendungsverzeichnis ab. INI-Datei.|  
|[CWinApp::GetProfileString](#getprofilestring)|Ruft eine Zeichenfolge aus einem Eintrag in der Anwendungsverzeichnis ab. INI-Datei.|  
|[CWinApp::GetSectionKey](#getsectionkey)|Gibt Schlüssel HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection "Software".|  
|[CWinApp::HideApplication](#hideapplication)|Blendet die Anwendung vor dem schließen alle Dokumente aus.|  
|[CWinApp::HtmlHelp](#htmlhelp)|Ruft die `HTMLHelp` Windows-Funktion.|  
|[CWinApp:: InitInstance](#initinstance)|Außer Kraft setzen Sie, um die Initialisierung des Windows-Instanz, z. B. das Erstellen von Windows-Objekte auszuführen.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.|  
|[CWinApp::LoadCursor](#loadcursor)|Lädt eine Cursorressource.|  
|[CWinApp::LoadIcon](#loadicon)|Lädt die Symbolressource.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Lädt eine OEM Windows vordefinierten Cursor, die die **OCR_** Konstanten geben an, in WINDOWS. H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Lädt ein vordefiniertes Windows OEM-Symbol, das **OIC_** Konstanten geben an, in WINDOWS. H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Lädt eine Windows vordefinierten Cursor, die die **IDC_** Konstanten geben an, in WINDOWS. H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Lädt eine vordefinierte Symbol "Windows", die die **IDI_** Konstanten geben an, in WINDOWS. H.|  
|[CWinApp::OnDDECommand](#onddecommand)|Wird aufgerufen, durch das Framework als Antwort auf eine dynamischen Daten Datenaustausch (DDE)-Befehl ausgeführt.|  
|[OnIdle](#onidle)|Außer Kraft setzen Sie, um anwendungsspezifische Leerlaufzeit Verarbeitung auszuführen.|  
|[CWinApp:: OpenDocumentFile](#opendocumentfile)|Vom Framework aufgerufen wird, ein Dokument aus einer Datei zu öffnen.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|Analysiert einzelner Parameter und Flags in der Befehlszeile angegeben.|  
|[PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten, bevor sie an die Windows-Funktionen verteilt sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung nicht erreichen.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|Behandelt das Befehlszeilenargumente und Flags.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Fängt alle Ausnahmefehler, die von der Anwendung-Nachricht und Befehlshandler ausgelöst.|  
|[CWinApp::Register](#register)|Führt die benutzerdefinierte Registrierung.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Registriert die Anwendung den Neustart-Manager.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Bestimmt, ob der Neustart-Manager die Dateien erneut, die geöffnet waren geöffnet, als die Anwendung wurde unerwartet beendet.|  
|[CWinApp::RestartInstance](#restartinstance)|Verarbeitet einen Neustart der Anwendung vom Neustart-Manager initiiert werden.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Bestimmt, ob der Neustart-Manager die Dateien automatisch, beim Neustart der Anwendung wiederhergestellt.|  
|[CWinApp:: Run](#run)|Führt die Standard-Nachrichtenschleife. Außer Kraft setzen Sie, um die Nachrichtenschleife anzupassen.|  
|[CWinApp::RunAutomated](#runautomated)|Testet die Anwendung über die Befehlszeile für die **/Automation** Option. Veraltet. Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) nach dem Aufruf [ParseCommandLine](#parsecommandline).|  
|[CWinApp::RunEmbedded](#runembedded)|Testet die Anwendung über die Befehlszeile für die **/einbetten** Option. Veraltet. Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) nach dem Aufruf [ParseCommandLine](#parsecommandline).|  
|[CWinApp::SaveAllModified](#saveallmodified)|Der Benutzer aufgefordert, alle geänderten Dokumente speichern.|  
|[CWinApp::SelectPrinter](#selectprinter)|Wählt einen Drucker, die zuvor durch einen Benutzer über ein Dialogfeld Drucken angegeben.|  
|[CWinApp::SetHelpMode](#sethelpmode)|Legt fest, und den Typ der Hilfe von der Anwendung verwendeten initialisiert.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Bestimmt, ob der Neustart-Manager eine Anwendung stellt wieder her, die unerwartet beendet.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Intervallen zu öffnen.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Bestimmt, ob der Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Bestimmt, ob die Anwendung den Neustart-Manager unterstützt.|  
|[CWinApp::Unregister](#unregister)|Hebt die Registrierung auf alle bekannten vom registriert werden die `CWinApp` Objekt.|  
|[CWinApp::WinHelp](#winhelp)|Ruft die `WinHelp` Windows-Funktion.|  
|[CWinApp:: WriteProfileBinary](#writeprofilebinary)|Schreibt binäre Daten in einen Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
|[CWinApp:: Writeprofileint](#writeprofileint)|Schreibt eine ganze Zahl auf einen Eintrag in der Anwendungsverzeichnis an. INI-Datei.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|Schreibt eine Zeichenfolge in einen Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Ermöglicht es dem Benutzer um Datendateien vom Windows-Datei-Manager zu öffnen.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Lädt-Standard. INI-Datei und ermöglicht die MRU-Datei-Funktion.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|UMSCHALT + F1-Hilfe in der Anwendung verarbeitet werden.|  
|[CWinApp::OnFileNew](#onfilenew)|Implementiert die `ID_FILE_NEW` Befehl.|  
|[CWinApp::OnFileOpen](#onfileopen)|Implementiert die `ID_FILE_OPEN` Befehl.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Implementiert die `ID_FILE_PRINT_SETUP` Befehl.|  
|[CWinApp::OnHelp](#onhelp)|Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|Verarbeitet die Befehle `ID_HELP_FINDER` und `ID_DEFAULT_HELP`.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|Verarbeitet den Befehl `ID_HELP_INDEX` und stellt ein standardmäßiges Hilfethema bereit.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|Verarbeitet den Befehl `ID_HELP_USING`.|  
|[CWinApp:: RegisterShellFileTypes](#registershellfiletypes)|Registriert alle Anwendung Dokumenttypen mit den Windows-Datei-Manager.|  
|[CWinApp::SetAppID](#setappid)|Explizit festlegt Anwendungsbenutzer Modell-ID für die Anwendung ein. Diese Methode sollte aufgerufen werden, bevor die Benutzer Benutzeroberfläche angezeigt werden (am besten geeignet ist der Anwendungskonstruktor).|  
|[CWinApp::SetRegistryKey](#setregistrykey)|Bewirkt, dass die Anwendungseinstellungen in der Registrierung gespeichert werden. INI-Dateien.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Hebt die Registrierung der Anwendungskonfigurationsdatei Dokumenttypen mit den Windows-Datei-Manager.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Gibt an, ob der Benutzer im Hilfe-Kontext-Modus (normalerweise mit UMSCHALT + F1 aufgerufen).|  
|[CWinApp::m_eHelpType](#m_ehelptype)|Gibt den Typ der Hilfe von der Anwendung verwendet.|  
|[CWinApp::m_hInstance](#m_hinstance)|Identifiziert die aktuelle Instanz der Anwendung an.|  
|[CWinApp:: M_lpcmdline](#m_lpcmdline)|Zeigt auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Gibt an, wie das Fenster befindet sich anfänglich angezeigt werden.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Ein Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server in-Place aktiv ist.|  
|[CWinApp::m_pszAppID](#m_pszappid)|Anwendung Benutzer Modell-ID.|  
|[CWinApp::m_pszAppName](#m_pszappname)|Gibt den Namen der Anwendung an.|  
|[CWinApp::m_pszExeName](#m_pszexename)|Der Modulname der Anwendung.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Der Pfad zu der Anwendung Hilfedatei.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Der Anwendungsverzeichnis zugeordnet ist. INI-Dateiname.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Dient zum Bestimmen des vollständigen Registrierungsschlüssels zum Speichern von Anwendungseinstellungen-Profil.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Flags, die bestimmen, wie die Neustart-Manager verhält.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Die Zeitdauer in Millisekunden zwischen speichert.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Ein Zeiger auf den Datenhandler für die Wiederherstellung für die Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Anwendungsobjekt bietet Memberfunktionen zum Initialisieren der Anwendung (und jede Instanz) und für die Ausführung der Anwendung.  
  
 Jede Anwendung, die Microsoft Foundation Classes verwendet, darf nur ein Objekt abgeleitet `CWinApp`. Dieses Objekt wird erstellt, wenn andere globale C++-Objekte erstellt werden und ist noch verfügbar, wenn Windows ruft die `WinMain` -Funktion, die durch die Microsoft Foundation Class-Bibliothek bereitgestellt wird. Deklarieren Sie die abgeleiteten `CWinApp` Objekt auf globaler Ebene.  
  
 Beim Ableiten einer Anwendungsklasse `CWinApp`, überschreiben die [InitInstance](#initinstance) Memberfunktion, die Anwendung im Hauptfenster Objekt zu erstellen.  
  
 Zusätzlich zu den `CWinApp` Memberfunktionen, die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen Zugriff auf Ihre `CWinApp` Objekt und anderen globalen Informationen:  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) erhält einen Zeiger auf die `CWinApp` Objekt.  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Ruft ein Handle für die aktuelle Anwendungsinstanz ab.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Ruft ein Handle für die Ressourcen der Anwendung ab.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) erhält einen Zeiger auf eine Zeichenfolge, die den Namen der Anwendung enthält. Alternativ können Sie ggf. einen Zeiger auf die `CWinApp` -Objekts `m_pszExeName` auf den Namen der Anwendung abrufen.  
  
 Finden Sie unter [CWinApp: die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md) Weitere Informationen über die `CWinApp` -Klasse, einschließlich einer Übersicht über die folgenden:  
  
- `CWinApp`-abgeleitet vom Anwendungs-Assistenten geschriebenen Code.  
  
- `CWinApp`die Rolle in der Ausführungsreihenfolge der Anwendung.  
  
- `CWinApp`in der Standardeinstellung Member funktionsimplementierungen werden.  
  
- `CWinApp`der Schlüssel Overridables.  
  
 Die **M_hPrevInstance** Datenmember nicht mehr vorhanden ist. Informationen zum Erkennen von eine Vorgängerinstanz des `CWinApp`, finden Sie im Knowledge Base-Artikel "Wie zu identifizieren eines vorherigen Instanz von einer Anwendung" (KB106385) unter [http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="adddoctemplate"></a>CWinApp:: AddDocTemplate  
 Rufen Sie diese Memberfunktion, um die Anwendung verwaltet die Liste der verfügbaren Dokumentvorlagen eine Dokumentvorlage hinzuzufügen.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `pTemplate`  
 Ein Zeiger auf die `CDocTemplate` hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten alle Dokumentvorlagen zu einer Anwendung vor dem Aufruf hinzufügen [RegisterShellFileTypes](#registershellfiletypes).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 Rufen Sie diese Memberfunktion hinzuzufügende `lpszPathName` auf die Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Der Pfad der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [LoadStdProfileSettings](#loadstdprofilesettings) Memberfunktion versucht, die aktuelle Liste der zuletzt verwendeten Datei zu laden, bevor Sie diese Memberfunktion verwenden.  
  
 Das Framework ruft diese Memberfunktion auf, wenn er eine Datei öffnet oder den Befehl "Speichern unter" zum Speichern einer Datei unter einem neuen Namen führt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 Vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpvParam`  
 Für zukünftige Verwendung reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn diese Methode erfolgreich ist; Wert ungleich NULL, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung den Neustart-Manager unterstützt, ruft Framework diese Funktion auf, wenn Ihre Anwendung unerwartet beendet wird.  
  
 Die standardmäßige Implementierung des `ApplicationRecoveryCallback` verwendet die `CDataRecoveryHandler` auf die Liste der derzeit geöffneten Dokumente in der Registrierung speichern. Diese Methode hat keine AutoSpeichern Dateien.  
  
 Überschreiben Sie zum Anpassen des Verhaltens dieser Funktion in einer abgeleiteten [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) oder übergeben Sie als Parameter an eine eigene Anwendung Wiederherstellungsmethode [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
##  <a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 Rufen Sie diese Memberfunktion zum Schließen aller geöffneten Dokumente vor dem Beenden an.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parameter  
 `bEndSession`  
 Gibt an, und zwar unabhängig davon, ob die Windows-Sitzung beendet wird. Es ist **"true"** wird die Sitzung beendet wird andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [HideApplication](#hideapplication) vor dem Aufruf `CloseAllDocuments`.  
  
##  <a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 Rufen Sie diese Memberfunktion, um einen Drucker-Gerätekontext (DC) aus den ausgewählten Drucker erstellen.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Ein Verweis auf einen Drucker-Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Drucker-Gerätekontext erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `CreatePrinterDC`Initialisiert den Gerätekontext, den Sie in als Verweis übergeben, damit Sie es zum Drucken verwenden können.  
  
 Wenn die Funktion erfolgreich ist, wenn Sie drucken abgeschlossen haben, müssen Sie den Gerätekontext zerstören. Lassen Sie den Destruktor, der die [CDC](../../mfc/reference/cdc-class.md) Objekt durchführen, oder explizit durch Aufrufen von durchführen [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).  
  
##  <a name="cwinapp"></a>CWinApp::CWinApp  
 Erstellt eine `CWinApp` Objekt auf und übergibt `lpszAppName` als den Namen der Anwendung gespeichert werden soll.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszAppName`  
 Eine auf Null endende Zeichenfolge, die den Namen der Anwendung enthält, den von Windows verwendet. Wenn dieses Argument nicht angegeben oder ist **NULL**, `CWinApp` verwendet die Ressourcenzeichenfolge **AFX_IDS_APP_TITLE** oder den Dateinamen der ausführbaren Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sollten Sie ein globales Objekt des Erstellen Ihrer `CWinApp`-Klasse. Sie sind nur möglich `CWinApp` Objekten in der Anwendung. Der Konstruktor speichert einen Zeiger auf die `CWinApp` Objekt, damit `WinMain` Member des Objekts initialisiert, und führen Sie die Anwendung können aufrufen.  
  
##  <a name="delregtree"></a>CWinApp::DelRegTree  
 Löscht eine bestimmte Registrierungsschlüssel und alle seine Unterschlüssel.  
  
```  
LONG DelRegTree(
    HKEY hParentKey,  
    const CString& strKeyName);

 
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *hParentKey*  
 Handle für einen Registrierungsschlüssel.  
  
 *strKeyName*  
 Der Name des Registrierungsschlüssels gelöscht werden soll.  
  
 *pTM*  
 Zeiger auf CAtlTransactionManager-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den angegebenen Schlüssel und Unterschlüssel löschen.  
  
##  <a name="domessagebox"></a>CWinApp::DoMessageBox  
 Das Framework ruft diese Memberfunktion, um ein Meldungsfeld für die globale Funktion zu implementieren [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPrompt*  
 Die Adresse des Texts in der MessageBox.  
  
 `nType`  
 Das Meldungsfeld [Stil](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).  
  
 `nIDPrompt`  
 Ein Index in eine Zeichenfolge der Hilfe-Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die gleichen Werte wie `AfxMessageBox`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Öffnen Sie ein Meldungsfeld nicht. Verwenden Sie `AfxMessageBox` stattdessen.  
  
 Überschreiben Sie diese Memberfunktion zum Anpassen Ihrer Verarbeitung anwendungsweite `AfxMessageBox` aufrufen.  
  
##  <a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 Diese Memberfunktion aufgerufen wird, durch das Framework implementieren [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nCode`  
 Wenn dieser Parameter 1 ist, wird ein Wartecursor angezeigt. Bei 0 wird der Wartecursor wiederhergestellt, ohne den Verweiszähler zu inkrementieren. Wenn-1 ist, endet der Wartecursor.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung wird ein Sanduhrcursor implementiert. `DoWaitCursor`verwaltet einen Verweiszähler dieser Planergruppe. Wenn positiv ist, wird die Sanduhrcursor angezeigt.  
  
 Während Sie normalerweise nicht aufrufen würde `DoWaitCursor` direkt, Sie können außer Kraft setzen diese Memberfunktion den Wartecursor ändern oder zusätzliche verarbeiten, während der Wartecursor angezeigt wird.  
  
 Verwenden Sie für eine einfachere, übersichtlichere Möglichkeit, einen Wartecursor zu implementieren, `CWaitCursor`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="enabled2dsupport"></a>CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 Ermöglicht die Anwendung D2D-Unterstützung. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Parameter  
 `d2dFactoryType`  
 Das Threadingmodell der D2D-Factory und die Ressourcen erstellt.  
  
 `writeFactoryType`  
 Ein Wert, der angibt, ob das Write-Factoryobjekt freigegeben oder isoliert wird  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn D2D-Unterstützung aktiviert, FALSE - wurde  
  
##  <a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 Rufen Sie diese Memberfunktion von innerhalb des Konstruktors der Ihre `CWinApp`-abgeleitete Klasse, um die HTMLHelp Hilfestellung bei der die Anwendung zu verwenden.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 Rufen Sie diese Funktion in der Regel aus Ihrer `InitInstance` Override "," Datendateien geöffnet werden, wenn sie die Dateien in den Windows-Datei-Manager doppelklicken Sie auf Ihre Anwendung Benutzern zu ermöglichen.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `RegisterShellFileTypes` Member-Funktion in Verbindung mit dieser Funktion, oder geben Sie ein. REG-Datei mit der Anwendung für die manuelle Registrierung Dokumenttypen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction  
 Ermöglicht die Interaktion der Taskleiste.  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob die Interaktion mit Windows 7-Taskleiste aktiviert werden soll ( `TRUE`), oder deaktiviert ( `FALSE`).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn Taskleiste Interaktion aktiviert oder deaktiviert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode muss vor der Erstellung des Hauptfensters aufgerufen werden, andernfalls bestätigt und gibt `FALSE`.  
  
##  <a name="exitinstance"></a>CWinApp:: ExitInstance  
 Vom Framework aufgerufen wird, innerhalb der **ausführen** Memberfunktion versucht, die dieser Instanz der Anwendung zu beenden.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Code der Anwendung beenden; 0 gibt an, keine Fehler, und geben einen Fehler an Werte größer als 0. Dieser Wert wird verwendet, als der Rückgabewert `WinMain`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht diese Memberfunktion überall jedoch innerhalb der **ausführen** Memberfunktion.  
  
 Die standardmäßige Implementierung dieser Funktion schreibt Framework-Optionen in der Anwendungsverzeichnis. INI-Datei. Überschreiben Sie diese Funktion zu bereinigen, wenn die Anwendung beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 Ruft die Eingabeparameter für die Anwendung Wiederherstellungsmethode ab.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Eingabedaten Standardparameter für die Anwendung Wiederherstellungsmethode.  
  
### <a name="remarks"></a>Hinweise  
 Gibt das Standardverhalten dieser Funktion `NULL`.  
  
 Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
##  <a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 Gibt die Zeitdauer, die der Neustart-Manager wartet, bis die Wiederherstellung Rückruffunktion zurückgegeben.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeitdauer in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung, die die Neustart-Manager wird beendet unerwartet registriert ist, wird die Anwendung versucht, offenen Dokumente zu speichern und die Wiederherstellung Callback-Funktion aufruft. Die Standardrückruffunktion für die Wiederherstellung ist [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
 Die Zeitdauer, die das Framework wartet, bis die Wiederherstellung Rückruffunktion zurückzugebenden ist der pingintervall. Sie können die pingintervall anpassen, indem überschreiben `CWinApp::GetApplicationRecoveryPingInterval` oder durch Angeben eines benutzerdefinierten Werts zu `RegisterWithRestartManager`.  
  
##  <a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 Gibt die Flags für den Neustart-Manager zurück.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Flags für den Neustart-Manager. Die Standardimplementierung gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Flags für den Neustart-Manager wirken sich nicht mit der Standardimplementierung. Sie sind für die zukünftige Verwendung bereitgestellt.  
  
 Beim Registrieren der Anwendung mit den Neustart-Manager mit, legen Sie die Flags [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
 Die möglichen Werte für den Neustart-Manager-Flags sind wie folgt aus:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="getappregistrykey"></a>CWinApp::GetAppRegistryKey  
 Gibt den Schlüssel für HKEY_CURRENT_USER\\\RegistryKey\ProfileName "Software".  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 ANWENDUNGSTASTE, wenn die Funktion erfolgreich ausgeführt wird; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 Ruft den Datenhandler für die Wiederherstellung für diese Instanz der Anwendung ab.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Wiederherstellung Datenhandler für diese Instanz der Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Jede Anwendung, die den Neustart-Manager verwendet haben muss eine Instanz von der [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Diese Klasse ist für die Überwachung geöffnete Dokumente und Dateien automatische Speicherung verantwortlich. Das Verhalten der `CDataRecoveryHandler` hängt von der Konfiguration des Neustart-Managers. Weitere Informationen finden Sie unter [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
 Diese Methode gibt `NULL` unter Betriebssystemen älter als [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Der Neustart-Manager wird nicht unterstützt, unter Betriebssystemen älter als [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Wenn die Anwendung noch nicht über ein Wiederherstellung Datenhandler ist, wird diese Methode erstellt ein und gibt einen Zeiger auf diese.  
  
##  <a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 Ruft die Position der ersten Vorlage in der Anwendung ab.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **POSITION** zurückgegebene Wert in einem Aufruf von [GetNextDocTemplate](#getnextdoctemplate) zum Abrufen der ersten [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.  
  
##  <a name="gethelpmode"></a>CWinApp::GetHelpMode  
 Ruft den Typ der Hilfe verwendet, die von der Anwendung ab.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Help-Typ, der von der Anwendung verwendet wird. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) für Weitere Informationen.  
  
##  <a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 Ruft die identifizierte Dokumentvorlage `pos`, dann legt `pos` auf die **POSITION** Wert.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** durch einen vorherigen Aufruf zurückgegebene Wert `GetNextDocTemplate` oder [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Der Wert wird auf der nächsten Position durch diesen Aufruf aktualisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNextDocTemplate` in einer Schleife vorwärts, wenn Sie die erste Position mit einem Aufruf von einrichten `GetFirstDocTemplatePosition`.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert ist ungültig. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
 Die abgerufene Dokumentvorlage ist die letzte verfügbar ist, klicken Sie dann den neuen Wert der `pos` festgelegt ist, um **NULL**.  
  
##  <a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 Rufen Sie diese Memberfunktion, um einen Drucker-Gerätekontext für das Drucken vorzubereiten.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>Parameter  
 *pPrintDlg*  
 Ein Zeiger auf eine [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ruft den aktuellen Druckerstandardeinstellungen von Windows ab. INI-Datei als erforderlich oder verwendet die letzte Druckerkonfiguration vom Benutzer in der Print-Installation festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="getprofilebinary"></a>CWinApp::GetProfileBinary  
 Rufen Sie diese Memberfunktion zum Abrufen von Binärdaten aus einem Eintrag in einem angegebenen Abschnitt der Registrierung für die Anwendung oder. INI-Datei.  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSection*  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.  
  
 *lpszEntry*  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Eintrag mit dem abzurufenden Wert enthält.  
  
 *ppData*  
 Verweist auf einen Zeiger, der die Adresse der Daten erhält.  
  
 *pBytes*  
 Verweist auf eine "uint", die die Größe der Daten (in Byte) empfangen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist daher nicht Groß-/ Kleinschreibung der Zeichenfolgen in der *LpszSection* und *LpszEntry* Parameter unterscheidet sich möglicherweise in Fällen.  
  
> [!NOTE]
> **GetProfileBinary** einen Puffer und gibt seine Adresse in \* *PpData*. Der Aufrufer ist verantwortlich für die Freigabe der Puffer mit **delete []**.  
  
> [!IMPORTANT]
>  Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CWinApp:: WriteProfileBinary](#writeprofilebinary).  
  
##  <a name="getprofileint"></a>CWinApp::GetProfileInt  
 Rufen Sie diese Memberfunktion auf, um den Ganzzahlwert aus einem Eintrag in einem angegebenen Abschnitt der Registrierung oder der INI-Datei einer Anwendung abzurufen.  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.  
  
 `lpszEntry`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Eintrag mit dem abzurufenden Wert enthält.  
  
 `nDefault`  
 Gibt den zurückzugebenden Standardwert an, wenn der Eintrag vom Framework nicht gefunden werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der dem bei erfolgreicher Funktion angegebene Eintrag folgende Ganzzahlwert der Zeichenfolge. Der Rückgabewert ist der Wert des `nDefault`-Parameters, wenn von der Funktion kein Eintrag gefunden wird. Der Rückgabewert ist null (0), wenn der dem angegebenen Eintrag entsprechende Wert keine ganze Zahl ist.  
  
 Diese Memberfunktion unterstützt Hexadezimalnotation für den Wert in der INI-Datei. Wenn Sie eine Zahl mit Vorzeichen abrufen, sollten Sie den Wert in `int` umwandeln.  
  
### <a name="remarks"></a>Hinweise  
 Bei dieser Memberfunktion wird die Groß-/Kleinschreibung nicht beachtet, sodass sich die Zeichenfolgen in den Parametern `lpszSection` und `lpszEntry` bei der Groß- und Kleinschreibung unterscheiden.  
  
> [!IMPORTANT]
>  Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CWinApp:: Writeprofileint](#writeprofileint).  
  
##  <a name="getprofilestring"></a>CWinApp::GetProfileString  
 Rufen Sie diese Memberfunktion zum Abrufen der Zeichenfolge, die einen Eintrag innerhalb des angegebenen Abschnitts in der Registrierung der Anwendung zugeordnet oder. INI-Datei.  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag, deren Zeichenfolge enthält abgerufen werden sollen. Dieser Wert darf nicht sein **NULL**.  
  
 `lpszDefault`  
 Verweist auf den Standard-Zeichenfolgenwert für den angegebenen Eintrag, wenn der Eintrag in der Initialisierungsdatei gefunden werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist die Zeichenfolge aus der Anwendungsverzeichnis. INI-Datei oder `lpszDefault` , wenn die Zeichenfolge nicht gefunden werden kann. Ist die maximale Zeichenfolgenlänge von Framework unterstützten `_MAX_PATH`. Wenn `lpszDefault` ist **NULL**, wird eine leere Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="getsectionkey"></a>CWinApp::GetSectionKey  
 Gibt den Schlüssel für HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection "Software".  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Der Name des Schlüssels abgerufen werden soll.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Abschnitt-Schlüssel, wenn die Funktion erfolgreich ausgeführt wird; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideapplication"></a>CWinApp::HideApplication  
 Rufen Sie diese Memberfunktion, um eine Anwendung vor dem Schließen von geöffneten Dokumente auszublenden.  
  
```  
void HideApplication();
```  
  
##  <a name="htmlhelp"></a>CWinApp::HtmlHelp  
 Rufen Sie diese Memberfunktion, um die HTMLHelp-Anwendung aufzurufen.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Gibt die zusätzliche Daten. Der verwendete Wert hängt vom Wert von der `nCmd` Parameter.  
  
 `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Einfluss auf die `dwData` Parameter, finden Sie unter der `uCommand` Parameter im über die HTMLHelp-API-Funktion im Windows SDK beschrieben.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch diese Funktion, um die HTMLHelp-Anwendung aufrufen.  
  
 Das Framework wird die HTMLHelp-Anwendung automatisch geschlossen, wenn die Anwendung beendet wird.  
  
##  <a name="initinstance"></a>CWinApp:: InitInstance  
 Windows kann mehrere Kopien desselben Programms gleichzeitig ausführen.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Anwendungsinitialisierung ist grundsätzlich in zwei Abschnitte unterteilt: einmalige anwendungsinitialisierung, die erfolgt die erste Ausführung des Programms und Initialisierung der Instanz, die jede führt Zeitdaten eine Kopie für die Anwendung ausgeführt wird, einschließlich der ersten. Implementierung des Frameworks `WinMain` ruft diese Funktion.  
  
 Überschreiben Sie `InitInstance` initialisiert werden, jede neue Instanz der Anwendung unter Windows ausgeführt wird. Überschreiben Sie in der Regel `InitInstance` das Hauptfenster-Objekt zu erstellen und Festlegen der `CWinThread::m_pMainWnd` -Datenmember auf dieses Fenster zeigen. Weitere Informationen zum überschreiben diese Memberfunktion auf, finden Sie unter [CWinApp: die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md).  
  
> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Beim Aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in Ihrer `InitInstance` außer Kraft setzen, geben Sie `COINIT_APARTMENTTHREADED` (statt `COINIT_MULTITHREADED`). Weitere Informationen finden Sie unter PRB: MFC-Anwendung nicht mehr reagiert, wenn Sie die Anwendung als eine Multithread-Apartment (828643) am initialisieren [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn `EnableTaskbarInteraction` aufgerufen wurde und das Betriebssystem ist Windows 7 oder höher.  
  
### <a name="remarks"></a>Hinweise  
 Taskleiste Interaktion bedeutet, dass MDI-Anwendung den Inhalt der untergeordnete MDI-Fenster in separaten im Registerkartenformat Miniaturansichten, die angezeigt werden angezeigt, wenn der Mauszeiger über die Taskleiste Anwendungsschaltfläche befindet.  
  
##  <a name="loadcursor"></a>CWinApp::LoadCursor  
 Lädt die Cursorressource mit dem Namen von `lpszResourceName` oder vom angegebenen `nIDResource` aus der aktuellen ausführbaren Datei.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Cursorressource enthält. Sie können eine `CString` für dieses Argument.  
  
 `nIDResource`  
 Die ID der Cursorressource. Eine Liste der Ressourcen, finden Sie unter [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 `LoadCursor`nur, wenn es nicht bereits geladen wurde, wird den Cursor in den Arbeitsspeicher geladen; Andernfalls wird ein Handle für die vorhandene Ressource abgerufen.  
  
 Verwenden der [LoadStandardCursor](#loadstandardcursor) oder [LoadOEMCursor](#loadoemcursor) Memberfunktion versucht, die vordefinierte Windows-Cursors zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>CWinApp::LoadIcon  
 Lädt die Symbolressource benannt, indem `lpszResourceName` oder vom angegebenen `nIDResource` aus der ausführbaren Datei.  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Symbolressource enthält. Sie können auch eine `CString` für dieses Argument.  
  
 `nIDResource`  
 ID-Nummer, der die Symbolressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 `LoadIcon`Lädt das Symbol an, nur dann, wenn es nicht bereits geladen wurde. Andernfalls wird ein Handle für die vorhandene Ressource abgerufen.  
  
 Sie können die [LoadStandardIcon](#loadstandardicon) oder [LoadOEMIcon](#loadoemicon) Memberfunktion versucht, die vordefinierte Windows-Symbole zugreifen.  
  
> [!NOTE]
>  Diese Memberfunktion Ruft die Win32-API-Funktion [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), laden die nur ein Symbol, dessen Größe entspricht, der **SM_CXICON zugeordnet** und **SM_CYICON zugeordnet** Metrikwerte System.  
  
##  <a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 Lädt das Windows vordefinierten Cursor-Ressource, die vom angegebenen `nIDCursor`.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCursor`  
 Ein **OCR_** manifest Konstante Bezeichner, der einen vordefinierten Windows Cursor angibt. Sie benötigen **#define OEMRESOURCE** vor **#include \<afxwin.h >** für den Zugriff auf die **OCR_** Konstanten in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadOEMCursor` oder [LoadStandardCursor](#loadstandardcursor) Memberfunktion versucht, die vordefinierte Windows-Cursors zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 Lädt das Windows vordefinierte Symbolressource gemäß `nIDIcon`.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDIcon`  
 Ein **OIC_** manifest Konstante Bezeichner, der angibt, einen vordefinierten Symbol "Windows". Sie benötigen **#define OEMRESOURCE** vor **#include \<afxwin.h >** für den Zugriff auf die **OIC_** Konstanten in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadOEMIcon` oder [LoadStandardIcon](#loadstandardicon) Memberfunktion versucht, die vordefinierte Windows-Symbole zugreifen.  
  
##  <a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 Lädt das Windows vordefinierten Cursor-Ressource, die `lpszCursorName` angibt.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszCursorName`  
 Ein **IDC_** manifest Konstante Bezeichner, der einen vordefinierten Windows Cursor angibt. Diese Bezeichner sind in WINDOWS definiert. H. Die folgende Liste enthält die möglichen vordefinierte Werte und die Bedeutung für `lpszCursorName`:  
  
- **IDC_ARROW** Standardpfeilcursor  
  
- **IDC_IBEAM** Standard-Text-Einfügemarke  
  
- **IDC_WAIT** Sanduhr Cursor verwendet, wenn Windows eine zeitintensive Aufgabe ausführt  
  
- **IDC_CROSS** Fadenkreuztool Cursor für die Auswahl  
  
- **IDC_UPARROW** Pfeil nach oben  
  
- **IDC_SIZE** veraltet und wird nicht unterstützt; verwenden Sie **IDC_SIZEALL**  
  
- **IDC_SIZEALL** ein Pfeil mit vier Spitzen. Der Cursor zu verwenden, um die Größe eines Fensters.  
  
- **IDC_ICON** veraltet und nicht unterstützt. Verwendung **IDC_ARROW**.  
  
- **IDC_SIZENWSE** Doppelpfeil mit am oberen linken und unteren rechten endet  
  
- **IDC_SIZENESW** Doppelpfeil mit am oberen rechten und unteren linken Ecke endet  
  
- **IDC_SIZEWE** horizontaler Pfeil mit zwei Spitzen  
  
- **IDC_SIZENS** vertikalen Doppelpfeil  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadStandardCursor` oder [LoadOEMCursor](#loadoemcursor) Memberfunktion versucht, die vordefinierte Windows-Cursors zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 Lädt das Windows vordefinierte Symbolressource, die `lpszIconName` angibt.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIconName`  
 Ein manifest Konstante Bezeichner, der angibt, einen vordefinierten Symbol "Windows". Diese Bezeichner sind in WINDOWS definiert. H. Eine Liste der möglichen vordefinierte Werte und deren Beschreibungen finden Sie die *LpIconName* im Parameters [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadStandardIcon` oder [LoadOEMIcon](#loadoemicon) Memberfunktion versucht, die vordefinierte Windows-Symbole zugreifen.  
  
##  <a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings  
 Rufen Sie diese Memberfunktion innerhalb der [InitInstance](#initinstance) Member-Funktion aktivieren und die Liste der zuletzt verwendeten (MRU)-Dateien geladen und Status zuletzt in der Vorschau anzeigen.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxMRU`  
 Die Anzahl der zuletzt verwendeten Dateien zu verfolgen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nMaxMRU` gleich 0 ist, keine MRU-Liste wird jedoch beibehalten.  
  
##  <a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **"True"** ist die Anwendung im Kontext Hilfemodus (konventionell mit UMSCHALT + F1 aufgerufen); andernfalls **"false"**.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Im Modus für Hilfe-Kontext der Cursor wird ein Fragezeichen, und der Benutzer über den Bildschirm verschieben. Überprüfen Sie dieses Flag aus, wenn Sie besondere Behandlung in den Hilfemodus implementieren möchten. `m_bHelpMode`ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 Flags, die bestimmen, wie die Neustart-Manager verhält.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Hinweise  
 Um den Neustart-Manager zu aktivieren, legen Sie `m_dwRestartManagerSupportFlags` auf das gewünschte Verhalten. Die folgende Tabelle zeigt die Flags, die verfügbar sind.  
  
|||  
|-|-|  
|Flag|Beschreibung|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|Die Anwendung mit registriert [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Der Neustart-Manager ist verantwortlich für die Anwendung neu zu starten, wenn es unerwartet beendet wird.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|Die Anwendung für den Neustart-Manager registriert ist, und der Neustart-Manager Ruft die Rückruffunktion Wiederherstellung beim Neustart der Anwendung. Die Standardrückruffunktion für die Wiederherstellung ist [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|AutoSpeichern aktiviert ist und der Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|AutoSpeichern aktiviert ist und der Neustart-Manager speichert alle Dokumente öffnen, in regelmäßigen Intervallen. Das Intervall wird definiert, indem [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|Der Neustart-Manager wird zuvor geöffneten Dokumenten nach dem Neustart der Anwendung eine unerwartete Beendigung geöffnet. Die [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md) kümmert sich um die Liste der geöffneten Dokumente speichern und wiederhergestellt werden.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|Der Neustart-Manager fordert den Benutzer automatisch gespeicherte Dateien wiederherstellen, nach dem Neustart der Anwendung. Die `CDataRecoveryHandler` Klasse fragt die Benutzer.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|Die Kombination `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, und `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|Die Kombination `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, und `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|Die Kombination `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, und `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|Die Kombination `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, und `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 Der Typ dieses Datenelements ist den enumerierten Typ **AFX_HELP_TYPE**, die definiert ist, in der `CWinApp` Klasse.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die **AFX_HELP_TYPE** Enumeration ist wie folgt definiert:  
  
```  
enum AFX_HELP_TYPE {  
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };  
```  
  
-   Rufen Sie zum Festlegen der Anwendung dienen dem HTML-Hilfe [SetHelpMode](#sethelpmode) , und geben Sie **AfxHTMLHelp**.  
  
-   Rufen Sie zum Festlegen der Anwendung dienen dem WinHelp `SetHelpMode` , und geben Sie **AfxWinHelp**.  
  
##  <a name="m_hinstance"></a>CWinApp::m_hInstance  
 Entspricht der `hInstance` Parameter übergeben von Windows zum `WinMain`.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hInstance` -Datenmember ist ein Handle für die aktuelle Instanz der Anwendung unter Windows ausgeführt wird. Dies ist die globale Funktion zurückgegebene [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance`ist eine öffentliche Variable des Typs `HINSTANCE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>CWinApp:: M_lpcmdline  
 Entspricht der `lpCmdLine` Parameter übergeben von Windows zum `WinMain`.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Hinweise  
 Zeigt auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt. Verwendung `m_lpCmdLine` auf Befehlszeilenargumente zuzugreifen, vom Benutzer eingegeben werden, wenn die Anwendung gestartet wurde. `m_lpCmdLine`ist eine öffentliche Variable des Typs `LPTSTR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 Die Zeitdauer in Millisekunden zwischen speichert.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Neustart-Manager, um AutoSpeichern geöffnete Dokumente in festgelegten Intervallen konfigurieren. Wenn Ihre Anwendung nicht AutoSpeichern-Dateien, hat dieser Parameter keine Auswirkungen.  
  
##  <a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 Entspricht der `nCmdShow` Parameter übergeben von Windows zum `WinMain`.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie `m_nCmdShow` als Argument beim Aufrufen von [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) für im Hauptfenster der Anwendung. `m_nCmdShow`ist eine öffentliche Variable des Typs `int`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd  
 Verwenden Sie dieses Datenelement, um einen Zeiger auf das Hauptfenster der Anwendung OLE-Container zu speichern, die OLE-Server-Anwendung direkte aktiviert hat.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Datenmember ist **NULL**, die Anwendung ist nicht in-Place aktiv.  
  
 Das Framework legt diese Membervariable fest, wenn das Rahmenfenster direktes von einer OLE-Container-Anwendung aktiviert ist.  
  
##  <a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 Ein Zeiger auf den Datenhandler für die Wiederherstellung für die Anwendung.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Datenhandler für die Wiederherstellung einer Anwendung überwacht, geöffnete Dokumente und speichert sie. Das Framework verwendet den Recovery Datenhandler automatisch gespeicherte Dateien wiederherstellen, wenn eine Anwendung neu gestartet wird, nachdem er unerwartet beendet wird. Weitere Informationen finden Sie unter [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
##  <a name="m_pszappname"></a>CWinApp::m_pszAppName  
 Gibt den Namen der Anwendung an.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Anwendungsname kann stammen aus den übergebenen Parameter die [CWinApp](#cwinapp) -Konstruktor oder, wenn nicht angegeben, auf die Ressourcenzeichenfolge mit der ID **AFX_IDS_APP_TITLE**. Wenn der Anwendungsname in der Ressource nicht gefunden wird, kommt es des Programms. EXE-Dateiname.  
  
 Die globale Funktion zurückgegebene [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuzuweisen `m_pszAppName`, müssen dynamisch auf dem Heap zugeordnet. Die `CWinApp` Destruktoraufrufe **freien**() mit dem this-Zeiger. Viele verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion die zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>CWinApp::m_pszExeName  
 Enthält den Namen der ausführbaren Anwendungsdatei ohne Erweiterung.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [M_pszAppName](#m_pszappname), dieser Name darf keine Leerzeichen enthalten. `m_pszExeName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuzuweisen `m_pszExeName`, müssen dynamisch auf dem Heap zugeordnet. Die `CWinApp` Destruktoraufrufe **freien**() mit dem this-Zeiger. Viele verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion die zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 Enthält den Pfad zu der Anwendung Hilfedatei.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig initialisiert das Framework `m_pszHelpFilePath` auf den Namen der Anwendung mit ". HLP"angefügt. Um den Namen der Hilfedatei zu ändern, legen Sie `m_pszHelpFilePath` , zeigen Sie auf eine Zeichenfolge, die den vollständigen Namen der gewünschten Hilfedatei enthält. Eine bequeme Möglichkeit hierzu ist in der Anwendungsverzeichnis [InitInstance](#initinstance) Funktion. `m_pszHelpFilePath`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuzuweisen `m_pszHelpFilePath`, müssen dynamisch auf dem Heap zugeordnet. Die `CWinApp` Destruktoraufrufe **freien**() mit dem this-Zeiger. Viele verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion die zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 Enthält den Namen der Anwendung. INI-Datei.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_pszProfileName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuzuweisen `m_pszProfileName`, müssen dynamisch auf dem Heap zugeordnet. Die `CWinApp` Destruktoraufrufe **freien**() mit dem this-Zeiger. Viele verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion die zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 Dient zum bestimmen, wo, in der Registrierung oder der INI-Datei, die profileinstellungen der Anwendung gespeichert werden.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Datenelement wird normalerweise als schreibgeschützt behandelt.  
  
-   Der Wert wird an einem Registrierungsschlüssel gespeichert. Der Name für die anwendungseinstellung für das Profil wird angefügt, auf den folgenden Registrierungsschlüssel: HKEY_CURRENT_USER/Software/LocalAppWizard-generierten /.  
  
 Wenn Sie einen Wert zuzuweisen `m_pszRegistryKey`, müssen dynamisch auf dem Heap zugeordnet. Die `CWinApp` Destruktoraufrufe **freien**() mit dem this-Zeiger. Viele verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion die zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>CWinApp::m_pszAppID  
 Anwendung Benutzer Modell-ID.  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncontexthelp"></a>CWinApp::OnContextHelp  
 UMSCHALT + F1-Hilfe in der Anwendung verarbeitet werden.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` Anweisung, um Ihre `CWinApp` -Klasse meldungszuordnung und Eintrags in einer Zugriffstastentabelle, in der Regel UMSCHALT + F1 sind, aktivieren Sie diese Memberfunktion hinzufügen.  
  
 `OnContextHelp`setzt die Anwendung in den Hilfemodus. Der Cursor geändert, um einen Pfeil und ein Fragezeichen ersetzt und der Benutzer können dann bewegen Sie den Mauszeiger und drücken Sie die linke Maustaste gedrückt, um eine (Dialogfeld), Fenster, Menüs oder Befehlsschaltfläche auszuwählen. Diese Memberfunktion Ruft den Hilfekontext für das Objekt unter dem Cursor und ruft die Windows-Funktion WinHelp mit diesem Hilfekontext.  
  
##  <a name="onddecommand"></a>CWinApp::OnDDECommand  
 Vom Framework aufgerufen, wenn das Hauptrahmenfenster eine DDE empfängt Nachricht ausgeführt.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszCommand*  
 Verweist auf eine DDE Befehlszeichenfolge, die von der Anwendung empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Befehl behandelt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft, ob der Befehl eine Anforderung ist, ein Dokument zu öffnen, und wenn dies der Fall ist, das angegebene Dokument öffnet. Der Windows-Datei-Manager sendet in der Regel solche Befehlszeichenfolgen DDE, wenn der Benutzer eine Datendatei doppelklickt. Überschreiben Sie diese Funktion behandelt andere DDE führen Befehle aus, z. B. den Befehl zum Drucken.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>CWinApp::OnFileNew  
 Implementiert die `ID_FILE_NEW` Befehl.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_NEW, OnFileNew )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, behandelt diese Funktion die Ausführung des Befehls neue Datei.  
  
 Finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md) Informationen zum Standardverhalten und wie Sie diese Memberfunktion überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileopen"></a>CWinApp::OnFileOpen  
 Implementiert die `ID_FILE_OPEN` Befehl.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, behandelt diese Funktion die Ausführung des Befehls Datei öffnen.  
  
 Informationen zum Standardverhalten und wie Sie diese Memberfunktion überschreiben, finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Implementiert die **ID_FILE_PRINT_SETUP** Befehl.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, verarbeitet diese Funktion die Ausführung des Befehls Drucken der Datei an.  
  
 Informationen zum Standardverhalten und wie Sie diese Memberfunktion überschreiben, finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onhelp"></a>CWinApp::OnHelp  
 Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel fügen Sie auch einen Zugriffstaste Eintrag für die F1-Taste. Aktivieren die F1-Taste wird nur eine Konvention, nicht erforderlich.  
  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP, OnHelp )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, wird vom Framework aufgerufen, wenn der Benutzer die F1-Taste drückt.  
  
 Die standardmäßige Implementierung dieser Nachrichtenhandler Funktion bestimmt den Hilfekontext, der das aktuelle Fenster, Dialogfeld oder Menüelement entspricht, und ruft dann die WINHELP. EXE-DATEI. Wenn kein Kontext verfügbar ist, verwendet die Funktion den Standardkontext.  
  
 Überschreiben Sie diese Memberfunktion zum Festlegen von des Hilfekontext auf einen anderen Wert als das Fenster, das Dialogfeld, Menüelement oder Symbolleisten-Schaltfläche, der gerade den Fokus besitzt. Rufen Sie `WinHelp` mit der gewünschten Hilfe-Kontext-ID  
  
##  <a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 Behandelt die **ID_HELP_FINDER** und **ID_DEFAULT_HELP** Befehle.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, das Framework ruft diese Meldungshandler Funktion, wenn der Benutzer der Anwendung den Befehl Hilfe Finder aufzurufenden auswählt `WinHelp` mit dem Standard **HELP_FINDER** Thema.  
  
##  <a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 Behandelt die **ID_HELP_INDEX** Befehls- und stellt ein standardmäßiges Hilfethema bereit.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Wenn aktiviert, das Framework ruft diese Funktion Meldungshandler Wenn der Benutzer der Anwendung zum Aufrufen den Hilfe-Befehl auswählt `WinHelp` mit dem Standard **HELP_INDEX** Thema.  
  
##  <a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 Behandelt die **ID_HELP_USING** Befehl.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung So aktivieren Sie diese Memberfunktion auf. Das Framework ruft diese Meldungshandler Funktion aus, wenn der Benutzer der Anwendung mit dem Befehl Hilfe verwenden, zum Aufrufen wird die `WinHelp` eine Anwendung mit dem Standard **HELP_HELPONHELP** Thema.  
  
##  <a name="onidle"></a>OnIdle  
 Überschreiben Sie diese Memberfunktion, um die Zeit im Leerlauf Verarbeitung durchzuführen.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Eine erhöht, jedes Mal `OnIdle` wird aufgerufen, wenn die Nachricht der Anwendungswarteschlange leer ist. Diese Anzahl wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die `lCount` Parameter, um die relative Dauer zu ermitteln, die Anwendung wurde ohne Verarbeitung einer Nachricht im Leerlauf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL im Leerlauf Verarbeitungszeit empfangen; 0, wenn keine weiteren Leerlaufzeit benötigt wird.  
  
### <a name="remarks"></a>Hinweise  
 `OnIdle`wird in der Standardeinstellung Nachrichtenschleife aufgerufen werden, wenn die Nachricht der Anwendungswarteschlange leer ist. Verwenden Sie die Außerkraftsetzung, um eigene Hintergrund Aufgaben im Leerlauf Ereignishandler aufzurufen.  
  
 `OnIdle`sollte zurückgeben 0 an, um anzugeben, dass keine Leerlaufzeiten erforderlich ist. Die `lCount` Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist und wird jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können Ihre verschiedenen im Leerlauf Routinen, die basierend auf diese Anzahl aufrufen.  
  
 Im folgenden werden Leerlaufschleifen-Verarbeitung zusammengefasst:  
  
1.  Wenn die Nachrichtenschleife in der Microsoft Foundation Class-Bibliothek die Nachrichtenwarteschlange überprüft, und es keine ausstehende Nachrichten findet, ruft es `OnIdle` für den Application-Objekt und gibt 0, als die `lCount` Argument.  
  
2. `OnIdle`Einige Verarbeitungsschritte ausführt, und gibt ein Wert ungleich NULL an, dass er sollte erneut aufgerufen werden, hierzu Weiterverarbeitung.  
  
3.  Die Nachrichtenschleife prüft die Nachrichtenwarteschlange erneut aus. Wenn keine Nachrichten mehr ausstehen, ruft es `OnIdle` erneut, erhöht die `lCount` Argument.  
  
4.  Schließlich `OnIdle` seine Leerlaufaufgaben Verarbeitung beendet und gibt 0 zurück. Das weist darauf hin, den Aufruf beendet die Nachrichtenschleife `OnIdle` bis die nächste Nachricht aus der Warteschlange empfangen wird, an welchem Punkt im Leerlauf Zyklus neu gestartet wird mit dem Argument auf 0 festgelegt.  
  
 Führen Sie langwierige Aufgaben während nicht `OnIdle` da Benutzereingaben bis zu Ihrer Anwendung verarbeiten kann nicht `OnIdle` zurückgibt.  
  
> [!NOTE]
>  Die standardmäßige Implementierung des `OnIdle` Updates Befehl Benutzeroberflächenobjekte wie Menüelemente und Symbolleisten-Schaltflächen und interne Daten Struktur Cleanup ausgeführt werden. Aus diesem Grund, wenn Sie außer Kraft setzen `OnIdle`, rufen Sie `CWinApp::OnIdle` mit der `lCount` in Ihrer überschriebene Version. Rufen Sie zuerst alle Basisklassen leerlaufverarbeitung (d. h., bis die Basisklasse `OnIdle` gibt 0 zurück). Wenn Sie müssen die Aufgaben ausführen, bevor die Basisklasse Verarbeitung abgeschlossen ist, überprüfen Sie die Implementierung der Basisklasse zum Auswählen der richtigen `lCount` währenddessen für Ihre Arbeit benötigen.  
  
 Wenn Sie nicht wünschen `OnIdle` um aufgerufen werden, wenn eine Nachricht aus der Warteschlange abgerufen wird, können Sie überschreiben die [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Wenn eine Anwendung einen sehr kurzen Zeitgeber festgelegt wurde oder vom System gesendet wird die **WM_SYSTIMER** Nachricht werden dann `OnIdle` wird wiederholt aufgerufen werden, und die Leistung beeinträchtigen.  
  
### <a name="example"></a>Beispiel  
 Die beiden folgenden Beispiele zeigen, wie mit `OnIdle`. Im erste Beispiel verarbeitet zwei im Leerlauf Aufgaben mithilfe der `lCount` Argument für die Aufgaben zu priorisieren. Die erste Aufgabe besteht hoher Priorität sollten, und Sie sie wann immer möglich. Der zweite Task ist weniger wichtig und sollte nur bei eine lange Pause Benutzereingaben vorgenommen werden. Beachten Sie den Aufruf der Basisklassenversion von `OnIdle`. Im zweite Beispiel wird eine Gruppe von Leerlaufaufgaben mit unterschiedlichen Prioritäten verwaltet.  
  
 [!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>CWinApp:: OpenDocumentFile  
 Das Framework ruft diese Methode, um die benannte öffnen [CDocument](../../mfc/reference/cdocument-class.md) Datei für die Anwendung.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszFileName`  
 Der Name der Datei geöffnet werden.  
  
 [in] `bAddToMRU`  
 `TRUE`Gibt an, dass das Dokument ist eine der letzten Dateien. `FALSE` gibt an, das Dokument ist nicht die aktuellsten Dateien.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDocument` Wenn erfolgreich; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Dokument, das diesem Namen ist bereits geöffnet ist, wird das erste Frame-Fenster, das das Dokument enthält den Fokus erhalten. Wenn eine Anwendung mehrere Dokumentvorlagen unterstützt, verwendet das Framework die Dateinamenerweiterung finden Sie die entsprechenden Dokumentvorlage zu dem Versuch, das Dokument geladen werden. Bei erfolgreicher Ausführung erstellt die Dokumentvorlage klicken Sie dann eine Rahmenfenster und die Ansicht für das Dokument.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 Rufen Sie diese Memberfunktion zum Analysieren von der Befehlszeile und senden die Parameter einzeln nacheinander, zu [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `rCmdInfo`  
 Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein neues MFC-Projekt mit dem Assistenten starten, wird den Assistenten zum Erstellen einer lokalen Instanz von `CCommandLineInfo`, und rufen dann `ProcessShellCommand` und `ParseCommandLine` in der [InitInstance](#initinstance) Memberfunktion. Über die Befehlszeile folgt die Route, die im folgenden beschrieben:  
  
1.  Nach dem Erstellen `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.  
  
2. `ParseCommandLine`Ruft dann `CCommandLineInfo::ParseParam` wiederholt, einmal für jeden Parameter.  
  
3. `ParseParam`füllt die `CCommandLineInfo` -Objekt, das dann an übergeben wird [ProcessShellCommand ein](#processshellcommand).  
  
4. `ProcessShellCommand`verarbeitet die Befehlszeilenargumente und Flags.  
  
 Beachten Sie, die Sie aufrufen können `ParseCommandLine` direkt nach Bedarf.  
  
 Eine Beschreibung der Flags, die Befehlszeile, finden Sie unter [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).  
  
##  <a name="pretranslatemessage"></a>PreTranslateMessage  
 Überschreiben Sie diese Funktion zu filtern, bevor sie an die Windows-Funktionen verteilt sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) die standardmäßige Implementierung führt Zugriffstaste Übersetzung, sodass Sie aufrufen müssen die `CWinApp::PreTranslateMessage` Memberfunktion in Ihrer überschriebene Version.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Ein Zeiger auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Nachricht in vollständig verarbeitet war `PreTranslateMessage` und sollten nicht weiter verarbeitet werden. 0 (null), wenn die Nachricht auf die übliche Weise verarbeitet werden soll.  
  
##  <a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
 Hookfunktion für das Framework ruft diese Memberfunktion filtern oder nur auf bestimmte Windows-Nachrichten reagiert.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 Gibt einen Hookcode. Diese Memberfunktion verwendet den Code, um zu bestimmen, wie verarbeitet`lpMsg.`  
  
 `lpMsg`  
 Ein Zeiger auf ein Windows [MSG](../../mfc/reference/msg-structure1.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Hookfunktion verarbeitet Ereignisse vor dem Senden an die Anwendung normal Nachricht verarbeiten.  
  
 Wenn Sie diese erweiterte Funktion überschreiben, müssen Sie die Basisklassenversion zum Verwalten des Frameworks aufrufen Verarbeitung zu verknüpfen.  
  
##  <a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 Diese Memberfunktion wird aufgerufen, indem [InitInstance](#initinstance) aus übergebenen Parameter akzeptiert die `CCommandLineInfo` identifizierte Objekt `rCmdInfo`, und führen Sie die angezeigte Aktion.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `rCmdInfo`  
 Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Shell-Befehl wurde erfolgreich verarbeitet wird. Bei 0 zurückgeben **"false"** aus [InitInstance](#initinstance).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein neues MFC-Projekt mit dem Assistenten starten, wird den Assistenten zum Erstellen einer lokalen Instanz von `CCommandLineInfo`, und rufen dann `ProcessShellCommand` und [ParseCommandLine](#parsecommandline) in die `InitInstance` Memberfunktion. Über die Befehlszeile folgt die Route, die im folgenden beschrieben:  
  
1.  Nach dem Erstellen `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.  
  
2. `ParseCommandLine`Ruft dann [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) wiederholt, einmal für jeden Parameter.  
  
3. `ParseParam`füllt die `CCommandLineInfo` -Objekt, das dann an übergeben wird `ProcessShellCommand`.  
  
4. `ProcessShellCommand`verarbeitet die Befehlszeilenargumente und Flags.  
  
 Die Datenmember von der `CCommandLineInfo` von identifizierten Objekts [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), sind die folgenden Enumerationstyps, der in definiert ist die `CCommandLineInfo` Klasse.  
  
```  
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };  
```
  
 Eine kurze Beschreibung jedes dieser Werte finden Sie unter `CCommandLineInfo::m_nShellCommand`.  
  
##  <a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 Das Framework ruft diese Memberfunktion auf, wenn der Handler eine in einem der Nachricht für Ihre Anwendung oder Befehlshandler ausgelöste Ausnahme nicht abfängt.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *e*  
 Ein Zeiger auf eine nicht abgefangene Ausnahme.  
  
 `pMsg`  
 Ein [MSG](../../mfc/reference/msg-structure1.md) -Struktur, die Informationen über die Windows-Meldung enthält, die das Framework eine Ausnahme verursacht hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der an Windows zurückgegeben werden sollen. Normalerweise ist dies 0L für Windows-Nachrichten, 1L ( **"true"**) für Command-Meldungen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nicht direkt auf.  
  
 Die Standardimplementierung von dieser Memberfunktion erstellt ein Meldungsfeld an. Wenn die nicht abgefangene Ausnahme mit einem Menü, eine Symbolleiste oder ein Accelerator-Befehl stammt, zeigt das Meldungsfeld eine Meldung "Fehler bei Befehl"; Andernfalls wird die Fehlermeldung "Interner Anwendungsfehler" an.  
  
 Überschreiben Sie diese Memberfunktion zum globalen Behandlung der Ausnahmen bereitzustellen. Rufen Sie nur die Basisfunktionalität auf, wenn Sie im Meldungsfeld angezeigt werden soll.  
  
##  <a name="register"></a>CWinApp::Register  
 Führt alle Registrierungsaufgaben, die nicht von verarbeitet aus `RegisterShellFileTypes`.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt einfach "true" zurück. Überschreiben Sie diese Funktion, um alle benutzerdefinierten Registrierung anzugeben.  
  
##  <a name="registershellfiletypes"></a>CWinApp:: RegisterShellFileTypes  
 Rufen Sie diese Memberfunktion zum Registrieren aller Dokumenttypen für Ihre Anwendung mit dem Windows-Datei-Manager.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCompat`  
 `TRUE`Fügt die Registrierungseinträge für Shell-Befehle, die Druck- und drucken, sodass einen Benutzer das Drucken von Dateien direkt von der Shell oder ziehen die Datei mit einem Druckerobjekt. Darüber hinaus wird einen DefaultIcon Schlüssel hinzugefügt. Standardmäßig ist dieser Parameter `FALSE` Gründen der Abwärtskompatibilität.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht es dem Benutzer zu eine Datendatei, die von der Anwendung erstellt wird, durch Doppelklick aus in Datei-Manager zu öffnen. Rufen Sie `RegisterShellFileTypes` nach dem Aufruf [AddDocTemplate](#adddoctemplate) für jedes Dokument Vorlagen in Ihrer Anwendung. Rufen Sie auch die [EnableShellOpen](#enableshellopen) Memberfunktion, die beim Aufrufen von `RegisterShellFileTypes`.  
  
 `RegisterShellFileTypes`durchläuft die Liste der [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekten, die von die Anwendung verwaltet, und für jede Dokumentvorlage Einträge der Registrierungsdatenbank hinzugefügt, die Windows für dateizuordnungen verwaltet. Datei-Manager verwendet diese Einträge, um eine Datei zu öffnen, wenn der Benutzer es doppelklickt. Hierdurch entfällt die Notwendigkeit, liefern ein. REG-Datei mit der Anwendung.  
  
> [!NOTE]
> `RegisterShellFileTypes`funktioniert nur, wenn der Benutzer das Programm mit Administratorrechten ausgeführt wird. Wenn das Programm nicht über Administratorrechte verfügt, können sie Registrierungsschlüssel nicht ändern.  
  
 Wenn der Registrierungsdatenbank angegebene Dateierweiterung bereits mit einem anderen Dateiformat zuordnet, wird keine neue Zuordnung erstellt. Finden Sie unter der `CDocTemplate` Klasse für das Format von Zeichenfolgen, die diese Informationen registriert.  
  
##  <a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager  
 Registriert die Anwendung den Neustart-Manager.  
  
```  
virtual HRESULT RegisterWithRestartManager(
BOOL bRegisterRecoveryCallback,  
const CString& strRestartIdentifier);

 
virtual HRESULT RegisterWithRestartManager(
LPCWSTR pwzCommandLineArgs,  
DWORD dwRestartFlags,  
APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,  
LPVOID lpvParam,  
DWORD dwPingInterval,  
DWORD dwCallbackFlags);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bRegisterRecoveryCallback`|`TRUE`Gibt an, dass diese Instanz der Anwendung eine Rückruffunktion für die Wiederherstellung verwendet. `FALSE` gibt an, dass dies nicht der Fall. Das Framework Ruft die Rückruffunktion für die Wiederherstellung aus, wenn die Anwendung unerwartet beendet wird. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `strRestartIdentifier`|Die eindeutige Zeichenfolge, die diese Instanz des Neustart-Managers identifiziert wird. Die Neustart-Manager-Bezeichner ist für jede Instanz einer Anwendung eindeutig.|  
|[in] `pwzCommandLineArgs`|Eine Zeichenfolge, die alle zusätzlichen Argumente über die Befehlszeile enthält.|  
|[in] `dwRestartFlags`|Optionale Kennzeichen für den Neustart-Manager. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|[in] `pRecoveryCallback`|Die Rückruffunktion für die Wiederherstellung. Diese Funktion muss annehmen einer `LPVOID` Parameter als Eingabe- und der Rückgabewert eine `DWORD`. Die Standardrückruffunktion für die Wiederherstellung ist `CWinApp::ApplicationRecoveryCallback`.|  
|[in] `lpvParam`|Die Eingabeparameter für die Wiederherstellung Rückruffunktion. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `dwPingInterval`|Die Zeitdauer, die der Neustart-Manager wartet, bis die Wiederherstellung Rückruffunktion zurückgegeben. Dieser Parameter ist in Millisekunden.|  
|[in] `dwCallbackFlags`|Flags, die an die Rückruffunktion Recovery übergeben werden. Für zukünftige Verwendung reserviert.|  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung die Standard-MFC-Implementierung für die automatische Speicherung Dateien verwendet, verwenden Sie die einfache Version eines `RegisterWithRestartManager`. Verwenden Sie die komplexe Version des `RegisterWithRestartManager` , wenn die automatische Speicherung Verhalten der Anwendung angepasst werden soll.  
  
 Wenn Sie diese Methode mit einer leeren Zeichenfolge für Aufrufen `strRestartIdentifier`, `RegisterWithRestartManager` erstellt eine Zeichenfolge Eindeutiger Bezeichner für diese Instanz den Neustart-Manager.  
  
 Wenn eine Anwendung unerwartet beendet wird, wird der Neustart-Manager startet die Anwendung über die Befehlszeile neu und enthält den eindeutigen Bezeichner als optionales Argument neu gestartet. In diesem Szenario das Framework ruft `RegisterWithRestartManager` zweimal. Der erste Aufruf stammt [CWinApp:: InitInstance](#initinstance) mit einer leeren Zeichenfolge für den Zeichenfolgenbezeichner. Klicken Sie dann die Methode [CWinApp::ProcessShellCommand](#processshellcommand) Aufrufe `RegisterWithRestartManager` mit dem Neustart des eindeutigen Bezeichner.  
  
 Nachdem Sie eine Anwendung mit den Neustart-Manager registriert haben, überwacht der Neustart-Manager die Anwendung an. Wenn die Anwendung unerwartet beendet wird, ruft der Neustart-Manager die Rückruffunktion Wiederherstellung während der Prozess beendet wird. Die Neustart-Manager wartet die `dwPingInterval` auf eine Antwort von der Wiederherstellung Rückruffunktion. Wenn die Wiederherstellung Rückruffunktion innerhalb dieses Zeitraums nicht reagiert, beendet die Anwendung ohne die Rückruffunktion für die Wiederherstellung auszuführen.  
  
 Standardmäßig die DwRestartFlags werden nicht unterstützt, jedoch werden für die zukünftige Verwendung bereitgestellt. Die möglichen Werte für `dwRestartFlags` lauten wie folgt:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 Bestimmt, ob der Neustart-Manager die Dateien erneut, die geöffnet waren geöffnet, als die Anwendung wurde unerwartet beendet.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt die Neustart-Manager wieder, die zuvor geöffneten Dateien an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="restartinstance"></a>CWinApp::RestartInstance  
 Verarbeitet einen Neustart der Anwendung vom Neustart-Manager initiiert werden.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Wiederherstellung Datenhandler öffnet zuvor öffnen Sie Dokumente; `FALSE` , wenn der Datenhandler für die Wiederherstellung einen Fehler aufweist oder es keine zuvor geöffneten Dokumente sind.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung der Neustart-Manager neu gestartet wird, ruft das Framework diese Methode auf. Diese Methode ruft die Wiederherstellung Datenhandler ab und stellt die Dateien automatisch wieder her. Diese Methode ruft [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) zu bestimmen, ob der Benutzer möchte die Dateien automatisch wiederhergestellt.  
  
 Diese Methode gibt `FALSE` Wenn die [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) feststellt, dass es keine geöffneten Dokumente wurden. Wenn gab es keine offenen Dokumente, startet die Anwendung in der Regel.  
  
##  <a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 Bestimmt, ob der Neustart-Manager die Dateien automatisch, beim Neustart der Anwendung wiederhergestellt.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt die Neustart-Manager Wiederherstellungen automatisch gespeicherte Dateien an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="run"></a>CWinApp:: Run  
 Stellt eine Standard-Nachrichtenschleife.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` von zurückgegebene Wert `WinMain`.  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** erhält und Windows-Meldungen sendet, bis die Anwendung empfängt eine **WM_QUIT** Nachricht. Wenn die Nachricht der Anwendungswarteschlange derzeit keine Nachrichten enthält **ausführen** Aufrufe [OnIdle](#onidle) leerlaufzeitverarbeitung ausführen. Eingehende Nachrichten werden an die [PreTranslateMessage](#pretranslatemessage) Memberfunktion für spezielle Verarbeitung und dann in der Windows-Funktion **TranslateMessage** für die Standardtastatur Übersetzung; schließlich die  **DispatchMessage** Windows-Funktion wird aufgerufen.  
  
 **Führen Sie** wird selten überschrieben wird, aber Sie können überschreiben, um spezielle Verhalten bereitzustellen.  
  
##  <a name="runautomated"></a>CWinApp::RunAutomated  
 Rufen Sie diese Funktion, um zu bestimmen, ob die " **/Automation**"oder" **-Automatisierung**" Option vorhanden ist, der angibt, ob die Anwendung für die von einer Clientanwendung gestartet wurde.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Option gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls vorhanden, wird die Option in der Befehlszeile entfernt. Weitere Informationen über OLE-Automatisierung finden Sie im Artikel [Automatisierungsserver](../../mfc/automation-servers.md).  
  
##  <a name="runembedded"></a>CWinApp::RunEmbedded  
 Rufen Sie diese Funktion, um zu bestimmen, ob die " **/einbetten**"oder" **-Embedding**" Option vorhanden ist, der angibt, ob die Anwendung für die von einer Clientanwendung gestartet wurde.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Option gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls vorhanden, wird die Option in der Befehlszeile entfernt. Weitere Informationen zum Einbetten finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
##  <a name="saveallmodified"></a>CWinApp::SaveAllModified  
 Wird aufgerufen, durch das Framework zum Speichern aller Dokumente beim Hauptrahmenfenster für die Anwendung wird geschlossen, oder durch eine `WM_QUERYENDSESSION` Nachricht.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn sicher ist, die Anwendung beenden; 0, wenn Sie nicht sicher sind, um die Anwendung zu beenden.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung von dieser Memberfunktion Ruft die [SaveModified](../../mfc/reference/cdocument-class.md#savemodified) Memberfunktion wiederum für alle geänderten Dokumente innerhalb der Anwendung.  
  
##  <a name="selectprinter"></a>CWinApp::SelectPrinter  
 Rufen Sie diese Memberfunktion, um einen bestimmten Drucker auswählen, und lassen Sie den Drucker, der zuvor im Dialogfeld Drucken ausgewählt wurde.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hDevNames`  
 Ein Handle für ein [DEVNAMES](../../mfc/reference/devnames-structure.md) Struktur, die die Treiber, Geräte und Ausgabe Anschlussnamen, der einen bestimmten Drucker bezeichnet.  
  
 `hDevMode`  
 Ein Handle für ein [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) -Struktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckers angibt.  
  
 *bFreeOld*  
 Gibt den zuvor ausgewählten Drucker frei.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beide `hDevMode` und `hDevNames` sind **NULL**, `SelectPrinter` verwendet den Standarddrucker.  
  
##  <a name="sethelpmode"></a>CWinApp::SetHelpMode  
 Legt die Anwendung Help Typ fest.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>Parameter  
 `eHelpType`  
 Gibt den Typ der Hilfe zu verwenden. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) für Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Legt die Anwendung Help Typ fest.  
  
 Ihr Anwendungstyp Hilfe auf HTMLHelp festlegen möchten, rufen Sie [EnableHTMLHelp](#enablehtmlhelp). Sobald Sie aufrufen `EnableHTMLHelp`, muss die Anwendung HTMLHelp wie die Hilfe-Anwendung verwenden. Wenn Sie ändern, um die WinHelp verwenden möchten, können Sie aufrufen `SetHelpMode` und `eHelpType` auf **AfxWinHelp**.  
  
##  <a name="setregistrykey"></a>CWinApp::SetRegistryKey  
 Bewirkt, dass die Anwendungseinstellungen in der Registrierung anstelle von INI-Dateien gespeichert werden.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszRegistryKey*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Schlüssels.  
  
 *nIDRegistryKey*  
 ID des eine Zeichenfolgenressource mit dem Namen des Registrierungsschlüssels.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion legt *M_pszRegistryKey*, dieser wird dann von verwendet die `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, und `WriteProfileString` Memberfunktionen der `CWinApp`. Wenn diese Funktion aufgerufen wurde, wird die Liste der zuletzt verwendeten (MRU)-Dateien auch in der Registrierung gespeichert. Der Registrierungsschlüssel ist in der Regel der Name eines Unternehmens. Befindet sich in einem Schlüssel in der folgenden Form: HKEY_CURRENT_USER\Software\\< Firmenname\>\\< Anwendungsname\>\\< Name des Abschnitts\>\\< Wert Namen\>.  
  
##  <a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 Bestimmt, ob der Neustart-Manager eine Anwendung stellt wieder her, die unerwartet beendet.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt die Neustart-Manager wiederhergestellt der Anwendung an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Intervallen zu öffnen.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager speichert Dokumente zu öffnen. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 Bestimmt, ob der Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager speichert Dokumente zu öffnen, wenn die Anwendung neu gestartet wird. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 Bestimmt, ob die Anwendung den Neustart-Manager unterstützt.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass die Anwendung den Neustart-Manager unterstützt. `FALSE` gibt an, die Anwendung hingegen nicht.  
  
##  <a name="unregister"></a>CWinApp::Unregister  
 Hebt die Registrierung aller Dateien, die durch das Anwendungsobjekt registriert.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die `Unregister` Funktion macht die Registrierung von des Anwendungsobjekts ausgeführt und die [registrieren](#register) Funktion. In der Regel beide Funktionen von MFC implizit aufgerufen werden und werden daher nicht in Ihrem Code angezeigt.  
  
 Überschreiben Sie diese Funktion zum Aufheben der Registrierung von benutzerdefinierten Schritte ausführen.  
  
##  <a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 Rufen Sie diese Memberfunktion zum Aufheben der Registrierung aller Dokumenttypen für Ihre Anwendung mit dem Windows-Datei-Manager.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="winhelp"></a>CWinApp::WinHelp  
 Rufen Sie diese Memberfunktion, um die WinHelp-Anwendung aufzurufen.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Gibt die zusätzliche Daten. Der verwendete Wert hängt vom Wert von der `nCmd` Parameter.  
  
 `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Einfluss auf die `dwData` Parameter, finden Sie unter der [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch diese Funktion, um die WinHelp-Anwendung aufrufen.  
  
 Das Framework wird die WinHelp-Anwendung automatisch geschlossen, wenn die Anwendung beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="writeprofilebinary"></a>CWinApp:: WriteProfileBinary  
 Rufen Sie diese Memberfunktion zum Schreiben von Binärdaten in den angegebenen Abschnitt der Registrierung für die Anwendung oder. INI-Datei.  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird er erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt.  
  
 `pData`  
 Verweist auf die zu schreibenden Daten.  
  
 `nBytes`  
 Enthält die Anzahl der zu schreibenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` CWinApp-Klasse, die zur Veranschaulichung einer Möglichkeit nutzen, `WriteProfileBinary` und `GetProfileBinary` kann von einer Funktion in einer MFC_Anwendung verwendet werden.  
  
 [!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileBinary](#getprofilebinary).  
  
##  <a name="writeprofileint"></a>CWinApp:: Writeprofileint  
 Rufen Sie diese Memberfunktion um den angegebenen Wert in den angegebenen Abschnitt der Registrierung für die Anwendung zu schreiben oder. INI-Datei.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird er erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt.  
  
 `nValue`  
 Enthält den Wert geschrieben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` CWinApp-Klasse, die zur Veranschaulichung einer Möglichkeit nutzen, `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, und `GetProfileInt` kann von einer Funktion in einer MFC_Anwendung verwendet werden.  
  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 Rufen Sie diese Memberfunktion, um die angegebene Zeichenfolge in den angegebenen Abschnitt der Registrierung für die Anwendung zu schreiben oder. INI-Datei.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird er erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt. Wenn dieser Parameter ist `NULL`, vom angegebenen Abschnitt `lpszSection` wird gelöscht.  
  
 `lpszValue`  
 Verweist auf die Zeichenfolge, die geschrieben werden. Wenn dieser Parameter ist `NULL`, der Eintrag gemäß der `lpszEntry` Parameter wurde gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="setappid"></a>CWinApp::SetAppID  
 Explizit festlegt Anwendungsbenutzer Modell-ID für die Anwendung ein. Diese Methode sollte aufgerufen werden, bevor die Benutzeroberfläche für den Benutzer angezeigt wird (der beste Ort wird der Anwendungskonstruktor).  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcszAppID`  
 Gibt an, die Anwendung Benutzer Modell-ID.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [CWinThread-Klasse](../../mfc/reference/cwinthread-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Vorgehensweise: Hinzufügen von Unterstützung für den Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)



