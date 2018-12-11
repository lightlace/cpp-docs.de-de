---
title: CWinApp-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 3f9afdf18fcaff0d3613b4204d8690f915079e7d
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178940"
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
|[CWinApp:: AddDocTemplate](#adddoctemplate)|Fügt eine Dokumentvorlage, die Anwendung die Liste der verfügbaren Dokumentvorlagen.|
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Ein Dateiname und die Liste der zuletzt verwendeten (MRU)-Dateien hinzugefügt.|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.|
|[CWinApp::CloseAllDocuments](#closealldocuments)|Schließt alle geöffneten Dokumente.|
|[CWinApp::CreatePrinterDC](#createprinterdc)|Erstellt einen Drucker-Gerätekontext.|
|[CWinApp::DelRegTree](#delregtree)|Löscht einen angegebenen Schlüssel und alle seine Unterschlüssel.|
|[CWinApp::DoMessageBox](#domessagebox)|Implementiert [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) für die Anwendung.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|Schaltet den Wartecursor an, und aus.|
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Ermöglicht die Anwendung D2D-Unterstützung. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Die Anwendung, anstatt WinHelp HTMLHelp implementiert.|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Ermöglicht die Interaktion der Taskleiste.|
|[CWinApp:: ExitInstance](#exitinstance)|Überschreiben Sie, um eine Bereinigung durchzuführen, wenn Ihre Anwendung beendet wird.|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Ruft den Eingabeparameter für die Methode der Anwendung ab.|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Gibt die Zeitspanne, die der Neustart-Manager wartet, bis die Wiederherstellung Callback-Funktion zurückgegeben.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Gibt die Flags für den Neustart-Manager zurück.|
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Gibt Schlüssel HKEY_CURRENT_USER\\"Software" \RegistryKey\ProfileName.|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Ruft den Datenhandler für die Wiederherstellung für diese Instanz der Anwendung ab.|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Ruft die Position der ersten Vorlage ab.|
|[CWinApp::GetHelpMode](#gethelpmode)|Ruft den Typ der Hilfe wird von der Anwendung ab.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Ruft die Position einer Dokumentvorlage ab. Rekursiv verwendet kann werden.|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Ruft die Standardwerte der Drucker-Gerät ab.|
|[CWinApp::GetProfileBinary](#getprofilebinary)|Ruft binäre Daten aus einem Eintrag in der Anwendung ab. INI-Datei.|
|[CWinApp::GetProfileInt](#getprofileint)|Ruft eine ganze Zahl aus einem Eintrag in der Anwendung ab. INI-Datei.|
|[CWinApp::GetProfileString](#getprofilestring)|Ruft eine Zeichenfolge aus einem Eintrag in der Anwendung ab. INI-Datei.|
|[CWinApp::GetSectionKey](#getsectionkey)|Gibt Schlüssel HKEY_CURRENT_USER\\"Software" \RegistryKey\AppName\lpszSection.|
|[CWinApp::HideApplication](#hideapplication)|Blendet die Anwendung vor dem schließen alle Dokumente aus.|
|[CWinApp::HtmlHelp](#htmlhelp)|Ruft die `HTMLHelp` Windows-Funktion.|
|[CWinApp:: InitInstance](#initinstance)|Außer Kraft setzen Sie, um die Initialisierung des Windows-Instanz, z. B. das Erstellen Ihrer Windows-Objekte auszuführen.|
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.|
|[CWinApp::LoadCursor](#loadcursor)|Lädt eine Cursorressource.|
|[CWinApp::LoadIcon](#loadicon)|Lädt die Symbolressource.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Lädt ein OEM Windows vordefinierten Cursor, die die **OCR_** Konstanten geben an, in WINDOWS. H.|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Lädt ein vordefiniertes Windows OEM-Symbol, das die **OIC_** Konstanten geben an, in WINDOWS. H.|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Lädt ein Windows vordefinierten Cursor, die die **IDC_** Konstanten geben an, in WINDOWS. H.|
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Lädt ein vordefiniertes Windows-Symbol, das die **IDI_** Konstanten geben an, in WINDOWS. H.|
|[CWinApp::OnDDECommand](#onddecommand)|Wird aufgerufen, durch das Framework als Reaktion auf eine dynamischen Daten Datenaustausch (DDE) Befehl ausführen.|
|[OnIdle](#onidle)|Überschreiben Sie, um anwendungsspezifische Leerlaufzeit, Verarbeitungsvorgänge auszuführen.|
|[CWinApp:: OpenDocumentFile](#opendocumentfile)|Vom Framework aufgerufen wird, ein Dokument aus einer Datei zu öffnen.|
|[CWinApp::ParseCommandLine](#parsecommandline)|Analysiert einzelne Parameter und die Flags in der Befehlszeile an.|
|[PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten, bevor sie für die Windows-Funktionen weitergeleitet werden [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung erreichen.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|Behandelt Befehlszeilenargumente und Flags.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Fängt alle nicht behandelte Ausnahmen, die von der Anwendung die Nachricht und befehlshandlern ausgelöst.|
|[CWinApp::Register](#register)|Benutzerdefinierte Registrierung ausführt.|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Registriert die Anwendung den Neustart-Manager.|
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Bestimmt, ob der Neustart-Manager die Dateien erneut, die geöffnet waren öffnet, wenn die Anwendung wurde unerwartet beendet.|
|[CWinApp::RestartInstance](#restartinstance)|Behandelt einen Neustart der Anwendung durch den Neustart-Manager initiiert.|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Bestimmt, ob es sich bei der Neustart-Manager die automatisch gespeicherte Dateien wiederhergestellt, wenn sie die Anwendung neu gestartet wird.|
|[CWinApp:: Run](#run)|Führt die Standardnachrichtenschleife an. Überschreiben Sie, um die Meldungsschleife anpassen.|
|[CWinApp::RunAutomated](#runautomated)|Testet die Anwendung in der Befehlszeile für die **/Automation** Option. Veraltet. Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) nach dem Aufruf [ParseCommandLine](#parsecommandline).|
|[CWinApp::RunEmbedded](#runembedded)|Testet die Anwendung in der Befehlszeile für die **/Embedding** Option. Veraltet. Verwenden Sie stattdessen den Wert in [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) nach dem Aufruf [ParseCommandLine](#parsecommandline).|
|[CWinApp::SaveAllModified](#saveallmodified)|Fordert den Benutzer, alle geänderten Dokumente zu speichern.|
|[CWinApp::SelectPrinter](#selectprinter)|Wählt einen Drucker, die zuvor durch einen Benutzer über ein Druckdialogfeld angezeigt.|
|[CWinApp::SetHelpMode](#sethelpmode)|Legt fest, und initialisiert den Typ der Hilfe von der Anwendung verwendet.|
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Bestimmt, ob der Neustart-Manager eine Anwendung wiederhergestellt werden, die unerwartet beendet.|
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Abständen zu öffnen.|
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Bestimmt, ob der Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Bestimmt, ob die Anwendung den Neustart-Manager unterstützt.|
|[CWinApp::Unregister](#unregister)|Hebt die Registrierung für alle bekannten vom registriert werden die `CWinApp` Objekt.|
|[CWinApp::WinHelp](#winhelp)|Ruft die `WinHelp` Windows-Funktion.|
|[CWinApp:: WriteProfileBinary](#writeprofilebinary)|Schreibt binäre Daten in einen Eintrag in der Anwendung. INI-Datei.|
|[CWinApp:: Writeprofileint](#writeprofileint)|Schreibt eine ganze Zahl auf einen Eintrag in der Anwendung an. INI-Datei.|
|[CWinApp::WriteProfileString](#writeprofilestring)|Schreibt eine Zeichenfolge in einen Eintrag in der Anwendung. INI-Datei.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinApp::EnableShellOpen](#enableshellopen)|Ermöglicht dem Benutzer um Datendateien aus dem Windows-Datei-Manager zu öffnen.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Lädt-Standard. INI-Datei und ermöglicht das MRU-Menü Datei Listenfunktion.|
|[CWinApp::OnContextHelp](#oncontexthelp)|Verarbeitet die UMSCHALT + F1-Hilfe in der Anwendung.|
|[CWinApp::OnFileNew](#onfilenew)|Implementiert die ID_FILE_NEW-Befehl.|
|[CWinApp::OnFileOpen](#onfileopen)|Implementiert die ID_FILE_OPEN-Befehl.|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Implementiert die ID_FILE_PRINT_SETUP-Befehl.|
|[CWinApp::OnHelp](#onhelp)|Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).|
|[CWinApp::OnHelpFinder](#onhelpfinder)|Verarbeitet die ID_HELP_FINDER und ID_DEFAULT_HELP-Befehle.|
|[CWinApp::OnHelpIndex](#onhelpindex)|Verarbeitet den ID_HELP_INDEX-Befehl aus, und stellt Sie ein standardmäßiges Hilfethema bereit.|
|[CWinApp::OnHelpUsing](#onhelpusing)|Verarbeitet die ID_HELP_USING-Befehl.|
|[CWinApp:: RegisterShellFileTypes](#registershellfiletypes)|Registriert alle für die Anwendung Dokumenttypen mit den Windows-Datei-Manager.|
|[CWinApp::SetAppID](#setappid)|Explizit festlegt Anwendungsbenutzer-Modell-ID für die Anwendung ein. Diese Methode sollte aufgerufen werden, bevor eine Benutzeroberfläche für Benutzer angezeigt werden (der beste Ort ist der Anwendungskonstruktor).|
|[CWinApp::SetRegistryKey](#setregistrykey)|Bewirkt, dass Anwendungseinstellungen in der Registrierung nicht gespeichert werden. INI-Dateien.|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Hebt die Registrierung aller Anwendungen Dokumenttypen mit den Windows-Datei-Manager.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Gibt an, ob der Benutzer im Modus der Hilfe-Kontext (in der Regel mit UMSCHALT + F1 aufgerufen).|
|[CWinApp::m_eHelpType](#m_ehelptype)|Gibt den Typ der Hilfe von der Anwendung verwendet.|
|[CWinApp::m_hInstance](#m_hinstance)|Gibt die aktuelle Instanz der Anwendung an.|
|[CWinApp:: M_lpcmdline](#m_lpcmdline)|Verweist auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Gibt an, wie das Fenster, zuerst angezeigt werden soll.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server direkt aktiv ist.|
|[CWinApp::m_pszAppID](#m_pszappid)|Anwendung Benutzer-Modell-ID.|
|[CWinApp::m_pszAppName](#m_pszappname)|Gibt den Namen der Anwendung an.|
|[CWinApp::m_pszExeName](#m_pszexename)|Der Modulname der Anwendung.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Der Pfad zur Hilfedatei der Anwendung.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Der Anwendung zugeordnet ist. INI-Dateiname.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Dient zum Bestimmen des vollständige Schlüssels für das Speichern von Anwendungseinstellungen-Profil.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Flags, die das Verhalten des Neustart-Managers bestimmt.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Die Zeitdauer in Millisekunden zwischen speichert.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Zeiger auf den Datenhandler für die Wiederherstellung für die Anwendung.|

## <a name="remarks"></a>Hinweise

Ein Anwendungsobjekt bietet Memberfunktionen zum Initialisieren der Anwendung (und jede Instanz) und für die Ausführung der Anwendung.

Jede Anwendung, der Microsoft Foundation Classes verwendet, darf nur ein Objekt abgeleitet `CWinApp`. Dieses Objekt wird erstellt, wenn andere globale C++-Objekte erstellt werden und ist bereits verfügbar, wenn Windows ruft die `WinMain` -Funktion, die durch die Microsoft Foundation Class-Bibliothek bereitgestellt wird. Deklarieren Ihrer abgeleiteten `CWinApp` Objekt auf globaler Ebene.

Beim Ableiten einer Anwendungsklasse von `CWinApp`, überschreiben die [InitInstance](#initinstance) Memberfunktion, die im Hauptfenster Objekt Ihrer Anwendung zu erstellen.

Zusätzlich zu den `CWinApp` Member-Funktionen, die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen Zugriff auf Ihre `CWinApp` Objekt und andere globale Informationen:

- [AfxGetApp](application-information-and-management.md#afxgetapp) erhält einen Zeiger auf die `CWinApp` Objekt.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) einen Handle für die aktuelle Anwendungsinstanz.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) einen Handle für die Ressourcen der Anwendung.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) erhält einen Zeiger auf eine Zeichenfolge, die den Namen der Anwendung enthält. Auch wenn man einen Zeiger auf die `CWinApp` -Objekts `m_pszExeName` um den Namen der Anwendung zu erhalten.

Finden Sie unter [CWinApp: Die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md) Weitere Informationen zu den `CWinApp` -Klasse, einschließlich einer Übersicht über die folgenden:

- `CWinApp`-Code geschrieben, die vom Anwendungs-Assistenten abgeleitet.

- `CWinApp`die Rolle in der Ausführungsreihenfolge Ihrer Anwendung.

- `CWinApp`ist standardmäßig Implementierungen von Memberfunktionen.

- `CWinApp`der Schlüssel / / Overridables.

Die `m_hPrevInstance` Datenmember nicht mehr vorhanden ist. Um zu bestimmen, ob eine andere Instanz der Anwendung ausgeführt wird, verwenden Sie einen benannten Mutex. Fällt den Mutex zu öffnen, sind keine anderen Instanzen der Anwendung auszuführen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="adddoctemplate"></a>  CWinApp:: AddDocTemplate

Rufen Sie diese Memberfunktion, um die Liste der verfügbaren Dokumentvorlagen eine Dokumentvorlage hinzuzufügen, die die Anwendung verwaltet.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Parameter

*pTemplate*<br/>
Ein Zeiger auf die `CDocTemplate` hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Sie sollten hinzufügen, dokumentieren Sie alle Vorlagen, um eine Anwendung vor dem Aufruf [RegisterShellFileTypes](#registershellfiletypes).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList

Rufen Sie diese Memberfunktion hinzufügen *LpszPathName* auf die Liste der zuletzt verwendeten Dateien.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Der Pfad der Datei.

### <a name="remarks"></a>Hinweise

Rufen Sie die [LoadStdProfileSettings](#loadstdprofilesettings) Memberfunktion, um die aktuelle Liste der zuletzt verwendeten Datei zu laden, bevor Sie diese Memberfunktion verwenden.

Das Framework ruft diese Memberfunktion öffnet eine Datei oder führt den Befehl "Speichern unter" eine Datei mit einem neuen Namen speichern.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback

Vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Parameter

*lpvParam*<br/>
[in] Für die zukünftige Verwendung reserviert.

### <a name="return-value"></a>Rückgabewert

0, wenn diese Methode erfolgreich ist; ungleich NULL, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung den Neustart-Manager unterstützt, ruft das Framework diese Funktion, wenn Ihre Anwendung unerwartet beendet wird.

Die standardmäßige Implementierung des `ApplicationRecoveryCallback` verwendet die `CDataRecoveryHandler` auf die Liste der aktuell geöffneten Dokumente in der Registrierung speichern. Diese Methode führt keine automatische Speicherung alle Dateien an.

Um das Verhalten anzupassen, überschreiben Sie diese Funktion in einer abgeleiteten [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) oder übergeben Sie als Parameter an Ihre eigenen Anwendung Wiederherstellungsmethode [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments

Rufen Sie diese Memberfunktion, um alle geöffneten Dokumente vor dem Beenden zu schließen.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parameter

*bEndSession*<br/>
Gibt an, und zwar unabhängig davon, ob die Windows-Sitzung beendet wird. Es ist "true", wenn die Sitzung beendet wird; andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie [HideApplication](#hideapplication) vor dem Aufruf `CloseAllDocuments`.

##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC

Rufen Sie diese Memberfunktion, um einen Drucker-Gerätekontext (DC) aus den ausgewählten Drucker erstellen.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Parameter

*dc*<br/>
Ein Verweis auf einen Drucker-Gerätekontext.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Drucker-Gerätekontext erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

`CreatePrinterDC` Initialisiert den Gerätekontext, den Sie in als Verweis übergeben, sodass Sie es zum Drucken verwenden können.

Wenn die Funktion erfolgreich ist, wenn Sie drucken abgeschlossen haben, müssen Sie den Gerätekontext vernichten. Lassen Sie den Destruktor, der die [CDC](../../mfc/reference/cdc-class.md) Objekt dafür, oder Sie können es explizit durch Aufrufen von [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).

##  <a name="cwinapp"></a>  CWinApp::CWinApp

Erstellt eine `CWinApp` Objekt und übergibt *LpszAppName* als den Namen der Anwendung gespeichert werden.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Parameter

*lpszAppName*<br/>
Eine Null-terminierte Zeichenfolge, die den Namen der Anwendung enthält, den Windows verwendet. Wenn dieses Argument nicht angegeben wird, oder NULL ist, `CWinApp` verwendet die Ressourcenzeichenfolge AFX_IDS_APP_TITLE oder den Dateinamen der ausführbaren Datei.

### <a name="remarks"></a>Hinweise

Sie sollten ein globales Objekt erstellen Ihre `CWinApp`-abgeleitete Klasse. Sie haben nur eine `CWinApp` Objekt in der Anwendung. Der Konstruktor speichert einen Zeiger auf die `CWinApp` Objekt, damit `WinMain` Member des Objekts Funktionen zu initialisieren und Ausführen der Anwendung aufrufen können.

##  <a name="delregtree"></a>  CWinApp::DelRegTree

Löscht einen bestimmten Registrierungsschlüssel und alle seine Unterschlüssel.

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

*hParentKey*<br/>
Handle für einen Registrierungsschlüssel.

*strKeyName*<br/>
Der Name des Registrierungsschlüssels gelöscht werden soll.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den angegebenen Schlüssel und dessen Unterschlüssel löschen.

##  <a name="domessagebox"></a>  CWinApp::DoMessageBox

Das Framework ruft diese Member-Funktion, um ein Meldungsfeld an, für die globale Funktion zu implementieren [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Parameter

*lpszPrompt*<br/>
Die Adresse des Texts in der MessageBox.

*nType*<br/>
Das Meldungsfeld [Stil](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).

*nIDPrompt*<br/>
Ein Index in eine Zeichenfolge der Hilfe-Kontext.

### <a name="return-value"></a>Rückgabewert

Gibt die gleichen Werte wie `AfxMessageBox`.

### <a name="remarks"></a>Hinweise

Rufen Sie nicht diese Member-Funktion, um ein Meldungsfeld zu öffnen. Verwenden Sie `AfxMessageBox` stattdessen.

Überschreiben Sie diese Memberfunktion zum Anpassen Ihrer gesamten Anwendung Verarbeitung `AfxMessageBox` aufrufen.

##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor

Diese Memberfunktion wird aufgerufen, durch das Framework zum Implementieren [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Parameter

*nCode*<br/>
Wenn dieser Parameter 1 ist, wird ein Wartecursor angezeigt. Wenn der Wert 0, wird der Wartecursor wiederhergestellt, ohne den Verweiszähler zu inkrementieren. Wenn-1 ist, endet der Wartecursor.

### <a name="remarks"></a>Hinweise

Der Standardwert implementiert ein Sanduhrcursor. `DoWaitCursor` verwaltet einen Verweiszähler. Wenn positiv ist, wird die Sanduhrcursor angezeigt.

Obwohl Sie normalerweise nicht aufrufen würde `DoWaitCursor` direkt, Sie können außer Kraft setzen diese Member-Funktion, um den Wartecursor zu ändern oder Sie zusätzliche Verarbeitung aus, während der Wartecursor angezeigt wird.

Verwenden Sie für eine einfachere und optimierte Möglichkeit, einen Wartecursor zu implementieren, `CWaitCursor`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport

Visual Studio 2010 SP1 wird benötigt.

Ermöglicht die Anwendung D2D-Unterstützung. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parameter

*d2dFactoryType*<br/>
Das Threadingmodell der D2D-Factory und die Ressourcen erstellt.

*writeFactoryType*<br/>
Ein Wert, der angibt, ob das Factoryobjekt für den Schreibzugriff freigegeben oder isoliert werden

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die D2D-Unterstützung aktiviert - wurde, andernfalls FALSE

##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp

Mit dieser Memberfunktion werden von innerhalb des Konstruktors, der Ihre `CWinApp`-abgeleitete Klasse, um die HTMLHelp Hilfe von Ihrer Anwendung verwenden.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Hinweise

##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen

Rufen Sie diese Funktion in der Regel aus Ihrer `InitInstance` außer Kraft setzen, damit Benutzer Ihrer Anwendung Datendateien geöffnet werden soll, wenn sie die Dateien in den Windows-Datei-Manager doppelklicken.

```
void EnableShellOpen();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die `RegisterShellFileTypes` Member funktionieren in Verbindung mit dieser Funktion, oder geben Sie ein. REG-Datei mit der Anwendung für die manuelle Registrierung von Dokumenttypen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction

Ermöglicht die Interaktion der Taskleiste.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
Gibt an, ob die Interaktion mit Windows 7-Taskleiste (TRUE) aktiviert werden soll, oder deaktiviert (FALSE).

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Taskleiste Interaktion aktiviert oder deaktiviert werden kann.

### <a name="remarks"></a>Hinweise

Diese Methode vor der Erstellung des Hauptfensters aufgerufen werden muss, andernfalls Assert-Vorgänge und gibt FALSE zurück.

##  <a name="exitinstance"></a>  CWinApp:: ExitInstance

Vom Framework aufgerufen wird, innerhalb der `Run` Memberfunktion versucht, diese Instanz der Anwendung zu beenden.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Rückgabewert

Der Anwendung Exitcode; 0 gibt an, keine Fehler, und geben einen Fehler an Werte größer als 0. Dieser Wert wird verwendet, als der Rückgabewert `WinMain`.

### <a name="remarks"></a>Hinweise

Rufen Sie nicht diese Memberfunktion von überall aus aber noch innerhalb der `Run` Member-Funktion.

Die Standardimplementierung dieser Funktion schreibt die Framework-Optionen in der Anwendung. INI-Datei. Überschreiben Sie diese Funktion zu bereinigen, wenn Ihre Anwendung beendet wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter

Ruft den Eingabeparameter für die Methode der Anwendung ab.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Rückgabewert

Die Standard-Eingabeparameter für die Anwendung Wiederherstellungsmethode.

### <a name="remarks"></a>Hinweise

Das Standardverhalten dieser Funktion gibt NULL zurück.

Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval

Gibt die Zeitspanne, die der Neustart-Manager wartet, bis die Wiederherstellung Callback-Funktion zurückgegeben.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Rückgabewert

Die Zeitdauer in Millisekunden.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung, die unerwartet beendet die Neustart-Manager registriert ist, wird die Anwendung versucht, geöffneten Dokumente speichern und ruft die Rückruffunktion für die Wiederherstellung. Ist die Standardrückruffunktion für die Wiederherstellung [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

Die Länge der Zeit, die das Framework wartet, bis die Wiederherstellung Callback-Funktion zurückgegeben wird das pingintervall. Sie können das pingintervall anpassen, indem das Überschreiben `CWinApp::GetApplicationRecoveryPingInterval` oder durch Angeben eines benutzerdefinierten Werts zu `RegisterWithRestartManager`.

##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags

Gibt die Flags für den Neustart-Manager zurück.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Rückgabewert

Die Flags für den Neustart-Manager. Die Standardimplementierung gibt 0 zurück.

### <a name="remarks"></a>Hinweise

Die Flags für den Neustart-Manager wirken sich nicht mit der Standardimplementierung. Sie werden für die zukünftige Verwendung bereitgestellt.

Festlegen der Flags, beim Registrieren der Anwendung mit den Neustart-Manager mit [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

Die möglichen Werte für den Neustart-Manager-Flags sind wie folgt aus:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey

Gibt den Schlüssel für HKEY_CURRENT_USER\\"Software" \RegistryKey\ProfileName.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Anwendungsschlüssel, wenn die Funktion erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler

Ruft den Datenhandler für die Wiederherstellung für diese Instanz der Anwendung ab.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Rückgabewert

Der Recovery Datenhandler für diese Instanz der Anwendung.

### <a name="remarks"></a>Hinweise

Jede Anwendung, die den Neustart-Manager verwendet, müssen eine Instanz der [CDataRecoveryHandler-Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Diese Klasse ist für die Überwachung der geöffneten Dokumente und Dateien für automatische Speicherung verantwortlich. Das Verhalten der `CDataRecoveryHandler` hängt von der Konfiguration des Neustart-Managers. Weitere Informationen finden Sie unter [CDataRecoveryHandler-Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).

Diese Methode gibt NULL zurück, auf Betriebssystemen vor Windows Vista. Der Neustart-Manager wird auf Betriebssystemen vor Windows Vista nicht unterstützt.

Wenn die Anwendung noch nicht über eine Datenhandler für die Wiederherstellung ist, wird diese Methode erstellt und gibt einen Zeiger darauf zurück.

##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition

Ruft die Position der ersten Vorlage in der Anwendung.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der für die Iteration oder Abrufen von Objekten Zeiger verwendet werden kann. NULL, wenn die Liste leer ist.

### <a name="remarks"></a>Hinweise

Verwenden Sie den-Positionswerts zurückgegeben wird, in einem Aufruf von [GetNextDocTemplate](#getnextdoctemplate) zum Abrufen der ersten [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.

##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode

Ruft den Typ der Hilfe wird von der Anwendung ab.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Rückgabewert

Der Help-Typ, der von der Anwendung verwendet wird. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) für Weitere Informationen.

##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate

Ruft die Dokumentvorlage identifizierte *pos*, legt dann *pos* auf den Wert der POSITION.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Ein Verweis auf eine Positionswert, der von einem vorherigen Aufruf zurückgegebene `GetNextDocTemplate` oder [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Der Wert wird durch diesen Aufruf an die nächste Position aktualisiert.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Sie können `GetNextDocTemplate` in einer Schleife Vorwärtsiteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetFirstDocTemplatePosition`.

Sie müssen sicherstellen, dass Ihre Positionswert gültig ist. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Die abgerufenen Dokumentvorlage ist die letzte verfügbar ist, klicken Sie dann den neuen Wert der *pos* auf NULL festgelegt ist.

##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults

Rufen Sie diese Memberfunktion, um einen Drucker-Gerätekontext für das Drucken vorzubereiten.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Parameter

*pPrintDlg*<br/>
Ein Zeiger auf eine [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Ruft die aktuellen Druckerstandardeinstellungen aus dem Windows ab. INI-Datei bei Bedarf oder die letzten Konfiguration festlegen, indem der Benutzer in der Print-Installation verwendet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>  CWinApp::GetProfileBinary

Rufen Sie diese Memberfunktion zum Abrufen von Binärdaten aus einem Eintrag in einem angegebenen Abschnitt der Registrierung von der Anwendung oder. INI-Datei.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.

*lpszEntry*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Eintrag mit dem abzurufenden Wert enthält.

*ppData*<br/>
Verweist auf einen Zeiger, der die Adresse der Daten zu erhalten.

*pBytes*<br/>
Verweist auf eine "uint", die die Größe der Daten (in Byte) erhält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist also nicht Groß-/ Kleinschreibung, die Zeichenfolgen in die *LpszSection* und *LpszEntry* Parameter können in Fällen unterscheiden.

> [!NOTE]
> `GetProfileBinary` weist einen Puffer und gibt dessen Adresse in \* *PpData*. Der Aufrufer ist verantwortlich für das Freigeben der Puffer mit **delete []**.

> [!IMPORTANT]
> Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Ein zusätzliches Beispiel finden Sie unter [CWinApp:: WriteProfileBinary](#writeprofilebinary).

##  <a name="getprofileint"></a>  CWinApp::GetProfileInt

Rufen Sie diese Memberfunktion auf, um den Ganzzahlwert aus einem Eintrag in einem angegebenen Abschnitt der Registrierung oder der INI-Datei einer Anwendung abzurufen.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.

*lpszEntry*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Eintrag mit dem abzurufenden Wert enthält.

*nDefault*<br/>
Gibt den zurückzugebenden Standardwert an, wenn der Eintrag vom Framework nicht gefunden werden kann.

### <a name="return-value"></a>Rückgabewert

Der dem bei erfolgreicher Funktion angegebene Eintrag folgende Ganzzahlwert der Zeichenfolge. Der Rückgabewert ist der Wert des der *nDefault* -Parameters, wenn die Funktion kein Eintrag gefunden wird. Der Rückgabewert ist null (0), wenn der dem angegebenen Eintrag entsprechende Wert keine ganze Zahl ist.

Diese Memberfunktion unterstützt Hexadezimalnotation für den Wert in der INI-Datei. Wenn Sie eine Ganzzahl mit Vorzeichen abrufen, sollten Sie wandeln Sie den Wert in eine **Int**.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist also nicht Groß-/ Kleinschreibung, die Zeichenfolgen in die *LpszSection* und *LpszEntry* Parameter können in Fällen unterscheiden.

> [!IMPORTANT]
> Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Ein zusätzliches Beispiel finden Sie unter [CWinApp:: Writeprofileint](#writeprofileint).

##  <a name="getprofilestring"></a>  CWinApp::GetProfileString

Rufen Sie diese Memberfunktion zum Abrufen der Zeichenfolge, die einen Eintrag innerhalb des angegebenen Abschnitts in der Registrierung von der Anwendung zugeordnet oder. INI-Datei.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt.

*lpszEntry*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Eintrag, dessen Zeichenfolge enthält abgerufen werden sollen. Dieser Wert darf nicht NULL sein.

*lpszDefault*<br/>
Verweist auf den Standardwert für die Zeichenfolge für den angegebenen Eintrag aus, wenn der Eintrag in der Initialisierungsdatei nicht gefunden werden kann.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist die Zeichenfolge, aus der Anwendung. INI-Datei oder *LpszDefault* , wenn die Zeichenfolge nicht gefunden werden kann. Die maximale Zeichenfolgenlänge, unterstützt durch das Framework ist _MAX_PATH. Wenn *LpszDefault* NULL ist, der Rückgabewert ist eine leere Zeichenfolge.

### <a name="remarks"></a>Hinweise

> [!IMPORTANT]
> Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).

##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey

Gibt den Schlüssel für HKEY_CURRENT_USER\\"Software" \RegistryKey\AppName\lpszSection.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Der Name des Schlüssels, der abgerufen werden.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Abschnittsschlüssel, wenn die Funktion erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="hideapplication"></a>  CWinApp::HideApplication

Rufen Sie diese Memberfunktion zum Ausblenden einer Anwendung vor dem Schließen von geöffneten Dokumente.

```
void HideApplication();
```

##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp

Rufen Sie diese Memberfunktion, um die HTMLHelp-Anwendung aufzurufen.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Parameter

*dwData*<br/>
Gibt zusätzliche Daten an. Der verwendete Wert hängt vom Wert von der *nCmd* Parameter.

*nCmd*<br/>
Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Auswirkungen auf die *DwData* Parameter finden Sie unter den *uCommand* Parameters im über die HTMLHelp-API-Funktion im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Das Framework ruft auch dieser Funktion können Sie die HTMLHelp-Anwendung aufrufen.

Das Framework wird die HTMLHelp-Anwendung automatisch geschlossen, wenn Ihre Anwendung beendet wird.

##  <a name="initinstance"></a>  CWinApp:: InitInstance

Windows ermöglicht es, mehrere Kopien desselben Programms zum gleichen Zeitpunkt ausgeführt wird.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Initialisierung erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Initialisieren der Anwendung ist im Prinzip in zwei Abschnitte unterteilt: einmalige anwendungsinitialisierung, die erfolgt die erste Ausführung des Programms und Initialisierung von Instanzen, die jeweils ausgeführt, wird bei der eine Kopie für die Anwendung ausgeführt wird, einschließlich der ersten Zeit. Die Framework Implementierung von `WinMain` ruft diese Funktion.

Außer Kraft setzen `InitInstance` zum Initialisieren der jede neue Instanz der Anwendung unter Windows ausgeführt wird. In der Regel, die Sie überschreiben `InitInstance` das Hauptfenster-Objekt zu erstellen und Festlegen der `CWinThread::m_pMainWnd` Datenmembers, der für dieses Fenster zeigen. Weitere Informationen zum Überschreiben dieser Memberfunktion finden Sie unter [CWinApp: Die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie aufrufen [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) in Ihre `InitInstance` außer Kraft setzen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled

Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn `EnableTaskbarInteraction` aufgerufen wurde und das Betriebssystem ist Windows 7 oder höher.

### <a name="remarks"></a>Hinweise

Taskleiste Interaktion bedeutet, dass es sich bei MDI-Anwendung den Inhalt der untergeordnete MDI-Fenster in den Miniaturansichten für separate Registerkarten angezeigt, die angezeigt werden, wenn der Mauszeiger über die Taskleiste Anwendungsschaltfläche befindet.

##  <a name="loadcursor"></a>  CWinApp::LoadCursor

Lädt die Cursorressource, die mit dem Namen von *LpszResourceName* oder gemäß *nIDResource* aus der aktuellen ausführbaren Datei.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Namen der Cursorressource enthält. Sie können eine `CString` für dieses Argument.

*nIDResource*<br/>
Die ID der Cursorressource. Eine Liste der Ressourcen, finden Sie unter [LoadCursor](/windows/desktop/api/winuser/nf-winuser-loadcursora) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

`LoadCursor` Lädt den Cursor in den Arbeitsspeicher an, nur dann, wenn es nicht bereits geladen wurde; Andernfalls wird ein Handle für die vorhandene Ressource abgerufen.

Verwenden der [LoadStandardCursor](#loadstandardcursor) oder [LoadOEMCursor](#loadoemcursor) Member-Funktion auf die vordefinierten Windows-Cursor.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>  CWinApp::LoadIcon

Lädt die Symbolressource mit dem Namen von *LpszResourceName* oder gemäß *nIDResource* aus der ausführbaren Datei.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Namen der Symbolressource enthält. Sie können auch eine `CString` für dieses Argument.

*nIDResource*<br/>
ID-Nummer der Symbolressource.

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Symbol, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

`LoadIcon` Laden das Symbol aus, nur dann, wenn es nicht bereits geladen wurde; Andernfalls wird ein Handle für die vorhandene Ressource abgerufen.

Sie können die [LoadStandardIcon](#loadstandardicon) oder [LoadOEMIcon](#loadoemicon) Member-Funktion auf die vordefinierten Windows-Symbole.

> [!NOTE]
> Diese Memberfunktion Ruft die Win32-API-Funktion [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona), kann das nur ein Symbol, dessen Größe der System-Metrikwerte SM_CXICON zugeordnet und SM_CYICON zugeordnet entspricht, laden.

##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor

Lädt das Windows vordefinierten Cursor-Ressource, die anhand des *nIDCursor*.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Parameter

*nIDCursor*<br/>
Ein **OCR_** manifest Konstanten Bezeichner, der angibt, einen vordefinierten Windows-Cursor. Sie benötigen `#define OEMRESOURCE` vor `#include \<afxwin.h>` für den Zugriff auf die **OCR_** Konstanten in WINDOWS. H.

### <a name="return-value"></a>Rückgabewert

Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden der `LoadOEMCursor` oder [LoadStandardCursor](#loadstandardcursor) Member-Funktion auf die vordefinierten Windows-Cursor.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon

Lädt das Windows vordefinierte Symbolressource, die gemäß *nIDIcon*.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Parameter

*nIDIcon*<br/>
Ein **OIC_** manifest Konstanten Bezeichner, der angibt, ein vordefiniertes Windows-Symbol. Sie benötigen `#define OEMRESOURCE` vor `#include \<afxwin.h>` für den Zugriff auf die **OIC_** Konstanten in WINDOWS. H.

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Symbol, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden der `LoadOEMIcon` oder [LoadStandardIcon](#loadstandardicon) Memberfunktion versucht, die vordefinierte Windows-Symbole zuzugreifen.

##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor

Lädt das Windows vordefinierten Cursor-Ressource, die *LpszCursorName* angibt.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Parameter

*lpszCursorName*<br/>
Ein **IDC_** manifest Konstanten Bezeichner, der angibt, einen vordefinierten Windows-Cursor. Diese Bezeichner werden in WINDOWS definiert. H. Die folgende Liste enthält die möglichen vordefinierte Werte und die Bedeutung für *LpszCursorName*:

- Standard IDC_ARROW Pfeilcursor.

- Standard IDC_IBEAM texteinfügung cursor

- IDC_WAIT Sanduhr Cursor verwendet, wenn Windows eine zeitaufwändige Aufgabe ausführt

- IDC_CROSS Fadenkreuztool Cursor für die Auswahl

- IDC_UPARROW-Pfeil, der gerade nach oben zeigt

- IDC_SIZE veraltet und nicht unterstützten; Verwenden Sie IDC_SIZEALL

- IDC_SIZEALL ein Vierfachpfeil. Der Cursor, verwenden Sie zum Ändern der Größe eines Fensters.

- IDC_ICON veraltet und nicht unterstützt. Verwenden Sie IDC_ARROW.

- IDC_SIZENWSE Doppelpfeil mit endet am oben links und rechts unten

- IDC_SIZENESW Doppelpfeil mit am oberen rechten und unteren linken Ecke endet

- IDC_SIZEWE horizontaler Pfeil mit zwei Spitzen

- Vertikale IDC_SIZENS STRG-Taste

### <a name="return-value"></a>Rückgabewert

Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden der `LoadStandardCursor` oder [LoadOEMCursor](#loadoemcursor) Member-Funktion auf die vordefinierten Windows-Cursor.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon

Lädt das Windows vordefinierte Symbolressource, die *LpszIconName* angibt.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Parameter

*lpszIconName*<br/>
Ein manifest Konstanten Bezeichner, der angibt, ein vordefiniertes Windows-Symbol. Diese Bezeichner werden in WINDOWS definiert. H. Eine Liste der möglichen vordefinierte Werte und deren Beschreibungen finden Sie die *LpIconName* Parameter im [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Symbol, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden der `LoadStandardIcon` oder [LoadOEMIcon](#loadoemicon) Memberfunktion versucht, die vordefinierte Windows-Symbole zuzugreifen.

##  <a name="loadstdprofilesettings"></a>  CWinApp::LoadStdProfileSettings

Rufen Sie diese Memberfunktion innerhalb der [InitInstance](#initinstance) Member-Funktion aktivieren, oder laden die Liste der zuletzt verwendeten (MRU)-Dateien, und zuletzt Vorschau Zustand.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Parameter

*nMaxMRU*<br/>
Die Anzahl der zuletzt geöffneten Dateien nachverfolgt werden soll.

### <a name="remarks"></a>Hinweise

Wenn *nMaxMRU* gleich 0 ist, kein MRU-Liste wird jedoch beibehalten.

##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode

TRUE, wenn die Anwendung im Modus der Hilfe-Kontext (konventionell aufgerufen mit UMSCHALT + F1) andernfalls "false".

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Hinweise

Im Modus der Hilfe-Kontext der Cursor zu einem Fragezeichen angegeben wird, und der Benutzer kann über den Bildschirm wechseln. Überprüfen Sie dieses Flag, wenn Sie besondere Behandlung, wenn in den Hilfemodus implementieren möchten. `m_bHelpMode` ist eine öffentliche Variable des Typs "bool".

##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags

Flags, die das Verhalten des Neustart-Managers bestimmt.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Hinweise

Um den Neustart-Manager zu aktivieren, legen `m_dwRestartManagerSupportFlags` auf das gewünschte Verhalten. Die folgende Tabelle zeigt die Flags, die verfügbar sind.

|||
|-|-|
|Flag|Beschreibung|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Die Anwendung registriert ist, mithilfe von [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Der Neustart-Manager ist verantwortlich für die Anwendung neu, wenn es unerwartet beendet wird.|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Die Anwendung mit den Neustart-Manager registriert ist, und der Neustart-Manager Ruft die Recovery-Rückruffunktion auf, wenn sie die Anwendung neu gestartet wird. Ist die Standardrückruffunktion für die Wiederherstellung [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Automatisches Speichern ist aktiviert und den Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Automatisches Speichern ist aktiviert und den Neustart-Manager speichert alle Dokumente öffnen, in regelmäßigen Intervallen. Das Intervall wird definiert, indem [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|
|-AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Der Neustart-Manager wird vorher geöffnete Dokumente nach dem Neustart der Anwendung eine unerwartete Beendigung geöffnet. Die [CDataRecoveryHandler-Klasse](../../mfc/reference/cdatarecoveryhandler-class.md) kümmert sich um die Liste der geöffneten Dokumente speichern und wiederherzustellen.|
|-AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Der Neustart-Manager mit der Aufforderung zum Wiederherstellen von automatisch gespeicherte Dateien nach dem Neustart der Anwendungs. Die `CDataRecoveryHandler` -Klasse fragt den Benutzer.|
|-AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|Die Union der AFX_RESTART_MANAGER_SUPPORT_RESTART AFX_RESTART_MANAGER_SUPPORT_RECOVER und AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES.|
|-AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|Die Union der AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL und AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|-AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|Die Union der AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES und AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Die union OfAFX_RESTART_MANAGER_SUPPORT_RECOVERY AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES und AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType

Der Typ dieses Datenelements ist den enumerierten Typ AFX_HELP_TYPE, die in definiert ist die `CWinApp` Klasse.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Hinweise

Die Enumeration AFX_HELP_TYPE wird wie folgt definiert:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Rufen Sie zum Festlegen der Anwendung Hilfe, um HTML-Hilfe [SetHelpMode](#sethelpmode) , und geben Sie `afxHTMLHelp`.

- Rufen Sie zum Festlegen der Anwendung-Hilfe, um die WinHelp `SetHelpMode` , und geben Sie `afxWinHelp`.

##  <a name="m_hinstance"></a>  CWinApp::m_hInstance

Entspricht der *hInstance* Parameter zu übergeben, von Windows auf `WinMain`.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Hinweise

Die `m_hInstance` -Datenmember ist ein Handle für die aktuelle Instanz der Anwendung unter Windows ausgeführt wird. Dies wird zurückgegeben, von der globalen Funktion [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance` ist eine öffentliche Variable des Typs HINSTANCE.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>  CWinApp:: M_lpcmdline

Entspricht der *LpCmdLine* Parameter zu übergeben, von Windows auf `WinMain`.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Hinweise

Verweist auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt. Verwendung `m_lpCmdLine` auf Befehlszeilenargumente zugreifen, vom Benutzer eingegeben wird, wenn die Anwendung gestartet wurde. `m_lpCmdLine` ist eine öffentliche Variable des Typs LPTSTR.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval

Die Zeitdauer in Millisekunden zwischen speichert.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Hinweise

Sie können den Neustart-Manager, um geöffnete Dokumente Autosave in regelmäßigen Abständen konfigurieren. Wenn Ihre Anwendung nicht automatisch gespeicherte Dateien, hat dieser Parameter keine Auswirkungen.

##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow

Entspricht der *nCmdShow* Parameter zu übergeben, von Windows auf `WinMain`.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Hinweise

Übergeben Sie `m_nCmdShow` als Argument beim Aufrufen [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) Hauptfenster der Anwendung. `m_nCmdShow` ist eine öffentliche Variable des Typs **Int**.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>  CWinApp::m_pActiveWnd

Verwenden Sie dieses Datenelement, um einen Zeiger auf das Hauptfenster der OLE-Container-Anwendung zu speichern, die OLE-Server-Anwendung direkt aktiviert hat.

### <a name="remarks"></a>Hinweise

Wenn dieses Datenelement NULL ist, ist die Anwendung nicht direkt aktiv.

Das Framework legt diese Membervariable fest, wenn das Rahmenfenster direkt von einer OLE-Container-Anwendung aktiviert ist.

##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler

Zeiger auf den Datenhandler für die Wiederherstellung für die Anwendung.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Hinweise

Der Datenhandler für die Wiederherstellung einer Anwendung überwacht die geöffneten Dokumenten und speichert sie. Das Framework verwendet den Datenhandler für die Wiederherstellung zum Wiederherstellen von Dateien von fortlaufend automatisch gespeichert, wenn eine Anwendung neu gestartet wird, nachdem es unerwartet beendet wird. Weitere Informationen finden Sie unter [CDataRecoveryHandler-Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).

##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName

Gibt den Namen der Anwendung an.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Hinweise

Den Namen der Anwendung aus der an übergebene Parameter stammen die [CWinApp](#cwinapp) Konstruktor oder, wenn nicht angegeben, um die Ressourcenzeichenfolge mit der ID des AFX_IDS_APP_TITLE. Wenn der Anwendungsname in der Ressource nicht gefunden wird, erfolgt über des Programms. Dateiname der EXE-Datei.

Von der globalen Funktion zurückgegebene [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName` ist eine öffentliche Variable des Typs **const Char**<strong>\*</strong>.

> [!NOTE]
> Wenn Sie einen Wert zuzuweisen `m_pszAppName`, es muss dynamisch auf dem Heap zugeordnet werden. Die `CWinApp` Destruktoraufrufe **kostenlose**(), mit dem this-Zeiger. Sie verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion der zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger für den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName

Enthält den Namen der ausführbaren Datei der Anwendung ohne Erweiterung.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Hinweise

Im Gegensatz zu [M_pszAppName](#m_pszappname), dieser Name darf keine Leerzeichen enthalten. `m_pszExeName` ist eine öffentliche Variable des Typs **const Char**<strong>\*</strong>.

> [!NOTE]
> Wenn Sie einen Wert zuzuweisen `m_pszExeName`, es muss dynamisch auf dem Heap zugeordnet werden. Die `CWinApp` Destruktoraufrufe **kostenlose**(), mit dem this-Zeiger. Sie verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion der zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger für den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath

Enthält den Pfad zu der Anwendung Hilfedatei.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Hinweise

Wird standardmäßig das Framework initialisiert `m_pszHelpFilePath` auf den Namen der Anwendung mit ". HLP"angefügt. Um den Namen der Hilfedatei zu ändern, legen `m_pszHelpFilePath` , zeigen Sie auf eine Zeichenfolge, die den vollständigen Namen der gewünschten Hilfedatei enthält. Eine bequeme Möglichkeit hierzu ist in der Anwendung [InitInstance](#initinstance) Funktion. `m_pszHelpFilePath` ist eine öffentliche Variable des Typs **const Char**<strong>\*</strong>.

> [!NOTE]
> Wenn Sie einen Wert zuzuweisen `m_pszHelpFilePath`, es muss dynamisch auf dem Heap zugeordnet werden. Die `CWinApp` Destruktoraufrufe **kostenlose**(), mit dem this-Zeiger. Sie verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion der zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger für den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName

Enthält den Namen der Anwendung. INI-Datei.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Hinweise

`m_pszProfileName` ist eine öffentliche Variable des Typs **const Char**<strong>\*</strong>.

> [!NOTE]
> Wenn Sie einen Wert zuzuweisen `m_pszProfileName`, es muss dynamisch auf dem Heap zugeordnet werden. Die `CWinApp` Destruktoraufrufe **kostenlose**(), mit dem this-Zeiger. Sie verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion der zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger für den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey

Verwendet, um zu bestimmen, wo, in der Registrierung oder der INI-Datei, die Profil-Anwendungseinstellungen gespeichert werden.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Hinweise

Dieses Datenelement wird normalerweise als schreibgeschützt behandelt.

- Der Wert wird auf einen Registrierungsschlüssel gespeichert. Der Name für die anwendungseinstellung für das Profil wird für den folgenden Registrierungsschlüssel angefügt: HKEY_CURRENT_USER/Software/LocalAppWizard-generiert /.

Wenn Sie einen Wert zuzuweisen `m_pszRegistryKey`, es muss dynamisch auf dem Heap zugeordnet werden. Die `CWinApp` Destruktoraufrufe **kostenlose**(), mit dem this-Zeiger. Sie verwenden möchten die `_tcsdup`()-Laufzeitbibliothek-Funktion der zuordnen möchten. Darüber hinaus können freigeben Sie den Speicher, der Zeiger für den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID

Anwendung Benutzer-Modell-ID.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Hinweise

##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp

Verarbeitet die UMSCHALT + F1-Hilfe in der Anwendung.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung und Eintrags in einer Zugriffstastentabelle, in der Regel UMSCHALT + F1 sind, aktivieren Sie diese Memberfunktion hinzufügen.

`OnContextHelp` Legt die Anwendung in den Hilfemodus. Des Elementtextes ändert sich durch einen Pfeil und Fragezeichen gebildet und der Benutzer können dann zeigen Sie auf und drücken Sie die linke Maustaste gedrückt, um ein Dialogfeld, Fenster, Menü oder Befehlsschaltfläche auszuwählen. Diese Memberfunktion Ruft das Objekt unter dem Cursor den Hilfekontext und ruft die Windows-Funktion WinHelp mit diesem Hilfekontext.

##  <a name="onddecommand"></a>  CWinApp::OnDDECommand

Vom Framework aufgerufen, wenn das Hauptrahmenfenster eine DDE empfängt Nachrichten führen.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Parameter

*lpszCommand*<br/>
Verweist auf eine DDE-Befehlszeichenfolge, die von der Anwendung empfangen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Befehl behandelt wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung überprüft, ob der Befehl eine Anforderung ist, ein Dokument zu öffnen, und wenn dies der Fall ist, das angegebene Dokument öffnet. Der Windows-Datei-Manager sendet solcher DDE-Befehlszeichenfolgen in der Regel, wenn der Benutzer eine Datei doppelklickt. Überschreiben Sie diese Funktion zur Behandlung von anderen DDE-Befehlen, wie z. B. den Befehl zum Drucken.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>  CWinApp::OnFileNew

Implementiert die ID_FILE_NEW-Befehl.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_NEW, OnFileNew )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, behandelt diese Funktion die Ausführung des Befehls Datei neu.

Finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md) Informationen zum Standardverhalten und Anleitungen, wie Sie diese Memberfunktion überschreiben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>  CWinApp::OnFileOpen

Implementiert die ID_FILE_OPEN-Befehl.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, behandelt diese Funktion die Ausführung des Befehls Datei öffnen.

Informationen zum Standardverhalten und Anleitungen, wie Sie diese Memberfunktion außer Kraft setzen, finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup

Implementiert die ID_FILE_PRINT_SETUP-Befehl.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, behandelt diese Funktion die Ausführung des Befehls Datei drucken.

Informationen zum Standardverhalten und Anleitungen, wie Sie diese Memberfunktion außer Kraft setzen, finden Sie unter [technischen Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>  CWinApp::OnHelp

Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Hinweise

In der Regel werden Sie auch einen Zugriffstaste Eintrag für die F1-Taste hinzufügen. Aktivieren die F1-Taste ist nur eine Konvention, nicht erforderlich.

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP, OnHelp )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, wird vom Framework aufgerufen, wenn der Benutzer die F1-Taste drückt.

Die Standardimplementierung dieser Funktion-Nachrichtenhandler bestimmt den Hilfekontext, der das aktuelle Fenster, das Dialogfeld oder Menüelement entspricht, und ruft dann die WINHELP. EXE-DATEI. Wenn kein Kontext zurzeit verfügbar ist, verwendet die Funktion den Standardkontext.

Überschreiben Sie diese Memberfunktion um den Hilfekontext auf etwas festzulegen, als das Fenster, das Dialogfeld, Menüelement oder Symbolleisten-Schaltfläche, der gerade den Fokus besitzt. Rufen Sie `WinHelp` helfen Sie mit den gewünschten Kontext-ID

##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder

Verarbeitet die ID_HELP_FINDER und ID_DEFAULT_HELP-Befehle.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, ruft das Framework diese Message-Handler-Funktion, wenn der Benutzer der Anwendung den aufzurufende Befehl Hilfe Finder auswählt `WinHelp` mit dem Standard **HELP_FINDER** Thema.

##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex

Verarbeitet den ID_HELP_INDEX-Befehl aus, und stellt Sie ein standardmäßiges Hilfethema bereit.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Wenn aktiviert, ruft das Framework Diese-Nachrichtenhandler-Funktion, wenn der Benutzer der Anwendung den aufzurufende Befehl den Index auswählt `WinHelp` mit dem Standard **HELP_INDEX** Thema.

##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing

Verarbeitet die ID_HELP_USING-Befehl.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Hinweise

Müssen Sie hinzufügen, eine `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` Anweisung, um Ihre `CWinApp` Nachricht "Map" gegen diese Member-Funktion zu aktivieren. Das Framework ruft diese Message-Handler-Funktion aus, wenn der Benutzer der Anwendung den aufzurufende Befehl Hilfe verwenden Wählt die `WinHelp` Anwendung mit dem Standard **HELP_HELPONHELP** Thema.

##  <a name="onidle"></a>  OnIdle

Überschreiben Sie diese Memberfunktion, um die Verarbeitung der Leerlauf-Ablaufzeitpunkt durchzuführen.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Ein Zähler erhöht, jedes Mal `OnIdle` wird aufgerufen, wenn die Nachricht der Anwendungswarteschlange leer ist. Diese Anzahl wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die *lCount* Parameter, um die relative Dauer zu ermitteln, die Anwendung wurde ohne Verarbeitung einer Nachricht im Leerlauf befindet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL im Leerlauf-Verarbeitungszeit empfangen; 0, wenn keine weiteren Leerlaufzeit benötigt wird.

### <a name="remarks"></a>Hinweise

`OnIdle` wird in die Standardnachrichtenschleife aufgerufen werden, wenn die Nachricht der Anwendungswarteschlange leer ist. Verwenden Sie die Außerkraftsetzung, um eigene Hintergrund im Leerlauf-Handler Aufgaben aufzurufen.

`OnIdle` sollte zurückgeben 0 an, um anzugeben, dass keine Leerlaufzeiten erforderlich ist. Die *lCount* Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist und wird jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können Ihre anderen im Leerlauf Routinen, die basierend auf diesen aufrufen.

Im folgenden wird zusammengefasst Leerlaufschleifen-Verarbeitung aus:

1. Wenn die Nachrichtenschleife in der Microsoft Foundation Class-Bibliothek die Nachrichtenwarteschlange überprüft und keine ausstehenden Nachrichten findet, ruft es `OnIdle` für die Application-Objekt und gibt 0 als die *lCount* Argument.

2. `OnIdle` führt eine Verarbeitung und gibt ein Wert ungleich NULL in letzterem Fall sollte erneut aufgerufen werden, hierzu weiter verarbeitet.

3. Die Nachrichtenschleife überprüft die Nachrichtenwarteschlange erneut an. Wenn keine Nachrichten ausstehend sind, ruft es `OnIdle` in diesem Fall erhöht der *lCount* Argument.

4. Schließlich `OnIdle` Verarbeitung alle im Leerlauf Aufgaben abgeschlossen hat, und gibt 0 zurück. Dadurch wird die Nachrichtenschleife den Aufruf beendet `OnIdle` bis die nächste Nachricht aus der Warteschlange empfangen wird, an diesem Punkt im Leerlauf Zyklus neu gestartet wird mit dem Argument auf 0 festgelegt.

Führen Sie nicht die langwierige Aufgaben während der `OnIdle` , da Ihre Anwendung nicht, eine Benutzereingabe, bis verarbeiten kann `OnIdle` zurückgibt.

> [!NOTE]
> Die standardmäßige Implementierung des `OnIdle` Updates Befehl Benutzeroberflächenobjekte wie z. B. Menüelemente und Symbolleistenschaltflächen und interne Struktur DatenBereinigung ausgeführt werden. Aus diesem Grund, wenn Sie außer Kraft setzen `OnIdle`, rufen Sie `CWinApp::OnIdle` mit der `lCount` in Ihrer außer Kraft gesetzte Version. Rufen Sie zuerst alle Basisklasse leerlaufverarbeitung (d. h., bis die Basisklasse `OnIdle` gibt 0 zurück). Wenn Sie möchten Aufgaben vor dem Abschluss der Basisklasse, überprüfen Sie die Implementierung der Basisklasse zum Auswählen der richtigen *lCount* der für Ihre Arbeit benötigen.

Wenn Sie nicht möchten `OnIdle` um aufgerufen, wenn eine Nachricht aus der Warteschlange abgerufen wird, können Sie überschreiben die [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Wenn eine Anwendung einen sehr kurzen Zeitgeber festgelegt wurde oder das System WM_SYSTIMER Senden der Nachricht, dann ist `OnIdle` wird wiederholt aufgerufen, und die Leistung beeinträchtigen.

### <a name="example"></a>Beispiel

Die folgenden zwei Beispiele zeigen, wie mit `OnIdle`. Im erste Beispiel verarbeitet zwei im Leerlauf Aufgaben, die mit der *lCount* Argument für die Aufgaben zu priorisieren. Die erste Aufgabe ist die hohe Priorität, und Sie sollten sie wann immer möglich tun. Der zweite Task ist nicht so wichtig und sollte nur während eine lange Pause bei Benutzereingaben vorgenommen werden. Beachten Sie den Aufruf der Basisklasse-Version des `OnIdle`. Im zweite Beispiel verwaltet eine Gruppe von Leerlaufaufgaben mit unterschiedlichen Prioritäten.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>  CWinApp:: OpenDocumentFile

Das Framework ruft diese Methode, um die benannte öffnen [CDocument](../../mfc/reference/cdocument-class.md) Datei für die Anwendung.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
[in] Der Name der Datei, die geöffnet werden.

*bAddToMRU*<br/>
[in] TRUE gibt an, dass das Dokument eine von der zuletzt verwendeten Dateien ist; FALSE gibt an, dass das Dokument nicht die zuletzt verwendeten Dateien ist.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CDocument` Wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn ein Dokument, das diesem Namen ist bereits geöffnet ist, wird das erste Rahmenfenster, das das Dokument enthält den Fokus erhalten. Wenn eine Anwendung mehrfache Dokumentvorlagen unterstützt, verwendet das Framework die Dateinamenerweiterung, um die entsprechenden Dokumentvorlage, versuchen Sie es zum Laden des Dokuments zu suchen. Wenn erfolgreich, erstellt die Dokumentvorlage ein Rahmenfenster und die Ansicht für das Dokument.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine

Rufen Sie diese Memberfunktion zum Analysieren von der Befehlszeile aus, und senden die Parameter einzeln nacheinander, zu [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parameter

*rCmdInfo*<br/>
Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Wenn Sie ein neues MFC-Projekt mithilfe des Assistenten starten, wird der Anwendungs-Assistent erstellt eine lokale Instanz von `CCommandLineInfo`, und rufen dann `ProcessShellCommand` und `ParseCommandLine` in die [InitInstance](#initinstance) Member-Funktion. Eine Befehlszeile folgt die Route, die unten beschrieben:

1. Nach dem Erstellen im `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.

2. `ParseCommandLine` Ruft dann `CCommandLineInfo::ParseParam` wiederholt wird, einmal für jeden Parameter.

3. `ParseParam` füllt die `CCommandLineInfo` -Objekt, das anschließend an [ProcessShellCommand erforderlich](#processshellcommand).

4. `ProcessShellCommand` verarbeitet die Befehlszeilenargumente und Flags.

Beachten Sie, die Sie aufrufen können `ParseCommandLine` direkt nach Bedarf.

Eine Beschreibung der Flags, die Befehlszeile finden Sie unter [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

##  <a name="pretranslatemessage"></a>  PreTranslateMessage

Außer Kraft setzen diese Funktion fenstermeldungen zu filtern, bevor sie für die Windows-Funktionen weitergeleitet werden [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) die Standardimplementierung nimmt der Zugriffstaste: Übersetzung, damit Sie aufrufen müssen die `CWinApp::PreTranslateMessage` Member-Funktion in Ihrer außer Kraft gesetzte Version.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Ein Zeiger auf eine [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) -Struktur, die zu verarbeitende Meldung enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht vollständig, im verarbeitet wurde `PreTranslateMessage` und sollten nicht weiter verarbeitet werden. NULL, wenn die Nachricht auf die übliche Weise verarbeitet werden soll.

##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter

Die Framework Hook-Funktion ruft diese Memberfunktion zum Filtern von und reagieren auf bestimmte Windows-Nachrichten.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parameter

*Code*<br/>
Gibt einen Hookcode. Diese Memberfunktion verwendet der Code, um zu bestimmen, wie verarbeiten *LpMsg.*

*lpMsg*<br/>
Ein Zeiger auf ein Windows [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Hookfunktion verarbeitet Ereignisse vor dem Senden an die normale Meldung von der Anwendung verarbeitet.

Wenn Sie diese erweiterte Funktion überschreiben, achten Sie darauf, ruft die Version der Basisklasse zum Verwalten des Frameworks Verarbeitung zu verknüpfen.

##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand

Diese Memberfunktion wird aufgerufen, indem [InitInstance](#initinstance) aus übergebenen Parameter akzeptiert die `CCommandLineInfo` identifizierte Objekt *rCmdInfo*, und führen Sie die angegebene Aktion.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Parameter

*rCmdInfo*<br/>
Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Shellbefehl erfolgreich verarbeitet wird. Wenn 0, wird "false" zurückgegeben [InitInstance](#initinstance).

### <a name="remarks"></a>Hinweise

Wenn Sie ein neues MFC-Projekt mithilfe des Assistenten starten, wird der Anwendungs-Assistent erstellt eine lokale Instanz von `CCommandLineInfo`, und rufen dann `ProcessShellCommand` und [ParseCommandLine](#parsecommandline) in die `InitInstance` Member-Funktion. Eine Befehlszeile folgt die Route, die unten beschrieben:

1. Nach dem Erstellen im `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.

2. `ParseCommandLine` Ruft dann [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) wiederholt wird, einmal für jeden Parameter.

3. `ParseParam` füllt die `CCommandLineInfo` -Objekt, das anschließend an `ProcessShellCommand`.

4. `ProcessShellCommand` verarbeitet die Befehlszeilenargumente und Flags.

Die Datenmember des der `CCommandLineInfo` identifizierte Objekt [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), sind von den folgenden Aufzählungstyp, der in definiert ist die `CCommandLineInfo` Klasse.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Eine kurze Beschreibung der einzelnen dieser Werte, finden Sie unter `CCommandLineInfo::m_nShellCommand`.

##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException

Das Framework ruft diese Memberfunktion auf, wenn der Handler eine Ausnahme in einem der Nachricht von Ihrer Anwendung oder Befehlshandler nicht abfängt.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*e*<br/>
Ein Zeiger auf eine nicht abgefangene Ausnahme.

*pMsg*<br/>
Ein [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) Struktur, die Informationen über die Windows-Meldung enthält, die das Framework eine Ausnahme verursacht hat.

### <a name="return-value"></a>Rückgabewert

Der Wert, der an Windows zurückgegeben werden soll. Normalerweise ist dies 0L für Windows-Meldungen, 1L (TRUE) für befehlsmeldungen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion nicht direkt auf.

Die Standardimplementierung von dieser Memberfunktion erstellt ein Meldungsfeld an. Wenn die nicht abgefangene Ausnahme mit einer Menüs, Symbolleisten oder Accelerator-Befehl stammt, zeigt das Meldungsfeld eine Meldung "Fehler bei Befehl"; Andernfalls wird eine "Interner Anwendungsfehler ist aufgetreten" angezeigt.

Überschreiben Sie diese Memberfunktion zum globalen Behandlung für die Ausnahmen bereitzustellen. Rufen Sie nur die grundlegende Funktionen auf, wenn das Meldungsfeld angezeigt werden soll.

##  <a name="register"></a>  CWinApp::Register

Führt alle Registrierungsaufgaben aus nicht vom behandelt `RegisterShellFileTypes`.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Die Standardimplementierung gibt einfach "true" zurück. Überschreiben Sie diese Funktion, um alle Registrierungsschritte für die benutzerdefinierte bereitstellen.

##  <a name="registershellfiletypes"></a>  CWinApp:: RegisterShellFileTypes

Rufen Sie diese Memberfunktion, um alle Dokumenttypen Ihrer Anwendung mit dem Windows-Datei-Manager zu registrieren.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Parameter

*bCompat*<br/>
[in] "True" fügt die Registrierungseinträge für Shell-Befehle, die Druck- und drucken, sodass Benutzer Dateien direkt aus der Shell oder ziehen die Datei auf ein Druckerobjekt zu drucken. Es fügt auch ein DefaultIcon-Schlüssel hinzu. Dieser Parameter ist standardmäßig "false" für die Abwärtskompatibilität.

### <a name="remarks"></a>Hinweise

Dadurch kann der Benutzer zum Öffnen einer Datendatei, die von der Anwendung durch Doppelklick aus in dem Datei-Manager erstellt. Rufen Sie `RegisterShellFileTypes` nach dem Aufruf von [AddDocTemplate](#adddoctemplate) für jede der Dokumentationsvorlagen in Ihrer Anwendung. Rufen Sie auch die [EnableShellOpen](#enableshellopen) Member-Funktion, die beim Aufrufen `RegisterShellFileTypes`.

`RegisterShellFileTypes` durchläuft die Liste der [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekten, die von die Anwendung verwaltet, und für jede Dokumentvorlage, in die Registrierungsdatenbank, Windows für die dateizuordnungen verwaltet, Einträge hinzugefügt. Datei-Manager verwendet diese Einträge, um eine Datei zu öffnen, wenn der Benutzer es doppelklickt. Dadurch entfällt die Notwendigkeit für den Versand ein. REG-Datei mit Ihrer Anwendung.

> [!NOTE]
> `RegisterShellFileTypes` funktioniert nur, wenn der Benutzer das Programm mit Administratorrechten ausgeführt wird. Wenn das Programm nicht über Administratorrechte verfügt, können sie Registrierungsschlüssel nicht ändern.

Wenn die Registrierungsdatenbank bereits eine bestimmte Dateierweiterung einen anderen Dateityp zugeordnet, wird keine neue Zuordnung erstellt. Finden Sie unter den `CDocTemplate` Klasse für das Format der Zeichenfolgen erforderlich, dass diese Informationen.

##  <a name="registerwithrestartmanager"></a>  CWinApp::RegisterWithRestartManager

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
|*bRegisterRecoveryCallback*|[in] TRUE gibt an, dass diese Instanz der Anwendung eine Rückruffunktion für die Wiederherstellung verwendet; FALSE gibt an, dass dies nicht der Fall. Das Framework Ruft die Rückruffunktion für die Wiederherstellung aus, wenn die Anwendung unerwartet beendet wird. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartIdentifier*|[in] Die eindeutige Zeichenfolge, die diese Instanz des Neustart-Managers identifiziert. Der Neustart-Manager-Bezeichner ist für jede Instanz einer Anwendung eindeutig.|
|*pwzCommandLineArgs*|[in] Eine Zeichenfolge, die zusätzliche Argumente über die Befehlszeile enthält.|
|*dwRestartFlags*|[in] Optionale Kennzeichen für den Neustart-Manager. Weitere Informationen finden Sie im Abschnitt "Hinweise".|
|*pRecoveryCallback*|[in] Die Rückruffunktion für die Wiederherstellung. Diese Funktion muss einen LPVOID-Parameter als Eingabe annehmen, und geben Sie einen DWORD-Wert zurück. Ist die Standardrückruffunktion für die Wiederherstellung `CWinApp::ApplicationRecoveryCallback`.|
|*lpvParam*|[in] Die Eingabeparameter für die Wiederherstellung Callback-Funktion. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|[in] Die Länge der Zeit, die der Neustart-Manager wartet, bis die Wiederherstellung Callback-Funktion zurückgegeben werden soll. Dieser Parameter ist in Millisekunden.|
|*dwCallbackFlags*|[in] Flags, die an die Wiederherstellung Callback-Funktion übergeben werden. Für zukünftige Verwendung reserviert.|

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung die MFC-Standardimplementierung für die automatische Speicherung von Dateien verwendet werden, verwenden Sie die einfache Version der `RegisterWithRestartManager`. Verwenden Sie die komplexen Version der `RegisterWithRestartManager` Wenn zum Anpassen des Autosave-Verhaltens der Anwendung verwendet werden sollen.

Wenn Sie diese Methode mit einer leeren Zeichenfolge für Aufrufen *StrRestartIdentifier*, `RegisterWithRestartManager` erstellt eine Zeichenfolge der eindeutige Bezeichner für diese Instanz beim Neustart-Manager.

Bei eine Anwendung unerwartet beendet wird, wird der Neustart-Manager startet die Anwendung über die Befehlszeile neu und enthält den eindeutigen Bezeichner wie ein optionales Argument neu starten. In diesem Szenario wird das Framework ruft `RegisterWithRestartManager` zweimal. Der erste Aufruf stammt [CWinApp:: InitInstance](#initinstance) mit einer leeren Zeichenfolge für den Zeichenfolgenbezeichner. Klicken Sie dann die Methode [CWinApp::ProcessShellCommand](#processshellcommand) Aufrufe `RegisterWithRestartManager` mit dem Neustart des eindeutigen Bezeichner.

Nachdem Sie eine Anwendung mit den Neustart-Manager registriert haben, überwacht der Neustart-Manager die Anwendung an. Wenn die Anwendung unerwartet beendet wird, ruft der Neustart-Manager die Wiederherstellung Callback-Funktion bei der Herunterfahren. Die Neustart-Manager wartet der *DwPingInterval* auf eine Antwort von der Wiederherstellung Callback-Funktion. Wenn die Rückruffunktion für die Wiederherstellung innerhalb dieses Zeitraums nicht antwortet, wird die Anwendung ohne Ausführung der Rückruffunktion für die Wiederherstellung beendet.

Standardmäßig wird die DwRestartFlags werden nicht unterstützt, jedoch werden für die zukünftige Verwendung bereitgestellt. Die möglichen Werte für *DwRestartFlags* lauten wie folgt:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart

Bestimmt, ob der Neustart-Manager die Dateien erneut, die geöffnet waren öffnet, wenn die Anwendung wurde unerwartet beendet.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass der Neustart-Manager die zuvor geöffneten Dateien erneut geöffnet wird; FALSE gibt an, dass der Neustart-Manager nicht der Fall ist.

##  <a name="restartinstance"></a>  CWinApp::RestartInstance

Behandelt einen Neustart der Anwendung durch den Neustart-Manager initiiert.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Datenhandler für die Wiederherstellung vorher geöffnete Dokumente wird geöffnet. "False", wenn der Datenhandler für die Wiederherstellung einen Fehler aufweist oder es keine vorher geöffnete Dokumente sind.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung der Neustart-Manager neu gestartet wird, ruft das Framework diese Methode auf. Diese Methode ruft den Datenhandler für Wiederherstellung und stellt die automatisch gespeicherte Dateien wieder her. Diese Methode ruft [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) zu bestimmen, ob der Benutzer die automatisch gespeicherte Dateien wiederherstellen möchte.

Diese Methode gibt "false" zurück, wenn die [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) feststellt, dass es keine geöffneten Dokumente gab. Wenn gab es keine offenen Dokumente, startet die Anwendung normalerweise.

##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart

Bestimmt, ob es sich bei der Neustart-Manager die automatisch gespeicherte Dateien wiederhergestellt, wenn sie die Anwendung neu gestartet wird.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Rückgabewert

"True" gibt an, dass der Neustart-Manager automatisch gespeicherte Dateien wiederhergestellt. FALSE gibt an, dass der Neustart-Manager nicht der Fall ist.

##  <a name="run"></a>  CWinApp:: Run

Stellt eine Standardnachrichtenschleife bereit.

```
virtual int Run();
```

### <a name="return-value"></a>Rückgabewert

Ein **Int** -Wert, der von zurückgegebene `WinMain`.

### <a name="remarks"></a>Hinweise

`Run` Ruft ab, und Windows-Meldungen sendet, bis die Anwendung eine WM_QUIT-Nachricht empfängt. Wenn die Nachricht der Anwendungswarteschlange derzeit keine Nachrichten von der enthält `Run` Aufrufe [OnIdle](#onidle) auszuführenden leerlaufzeitverarbeitung. Eingehende Nachrichten finden Sie unter der [PreTranslateMessage](#pretranslatemessage) Memberfunktion zur speziellen Verarbeitung, und klicken Sie dann an die Windows-Funktion `TranslateMessage` für die Standardtastatur Übersetzung; schließlich die `DispatchMessage` Windows-Funktion wird aufgerufen.

`Run` nur selten überschrieben wird, kann jedoch überschrieben werden, um besonderes Verhalten bereitzustellen.

##  <a name="runautomated"></a>  CWinApp::RunAutomated

Rufen Sie diese Funktion, um zu bestimmen, ob die " **/Automation**"oder" **-Automatisierung**"-Option vorhanden ist, der angibt, ob die Server-Anwendung von einer Clientanwendung gestartet wurde.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Option gefunden wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Falls vorhanden, wird die Option über die Befehlszeile entfernt. Weitere Informationen über OLE-Automatisierung finden Sie im Artikel [Automatisierungsserver](../../mfc/automation-servers.md).

##  <a name="runembedded"></a>  CWinApp::RunEmbedded

Rufen Sie diese Funktion, um zu bestimmen, ob die " **/Embedding**"oder" **-Embedding**"-Option vorhanden ist, der angibt, ob die Server-Anwendung von einer Clientanwendung gestartet wurde.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Option gefunden wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Falls vorhanden, wird die Option über die Befehlszeile entfernt. Weitere Informationen zum Einbetten finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).

##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified

Wird aufgerufen, durch das Framework alle Dokumente gespeichert werden soll, wenn der Anwendung Hauptrahmenfenster ist geschlossen werden oder über eine WM_QUERYENDSESSION-Nachricht.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn sicher ist, die die Anwendung zu beenden, 0, wenn Sie nicht sicher sind, um die Anwendung zu beenden.

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung von dieser Memberfunktion die [SaveModified](../../mfc/reference/cdocument-class.md#savemodified) Memberfunktion nacheinander für alle geänderten Dokumente innerhalb der Anwendung.

##  <a name="selectprinter"></a>  CWinApp::SelectPrinter

Rufen Sie diese Memberfunktion, um einen bestimmten Drucker auszuwählen, und lassen Sie den Drucker, der zuvor im Dialogfeld "Drucken" ausgewählt wurde.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Parameter

*hDevNames*<br/>
Ein Handle für ein [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) Struktur, die der Treiber, Gerät und Ausgabe-Anschlussnamen, der einen bestimmten Drucker bezeichnet.

*hDevMode-Feld*<br/>
Ein Handle für ein [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) -Struktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckers angibt.

*bFreeOld*<br/>
Gibt den zuvor ausgewählten Drucker frei.

### <a name="remarks"></a>Hinweise

Wenn beide *hDevMode-Feld* und *hDevNames* NULL sind, `SelectPrinter` verwendet den Standarddrucker.

##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode

Legt die Anwendung Help Typ fest.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Parameter

*eHelpType*<br/>
Gibt den Typ der Hilfe zur Verwendung an. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) für Weitere Informationen.

### <a name="remarks"></a>Hinweise

Legt die Anwendung Help Typ fest.

Um Ihrer Anwendung Hilfe Typ HTMLHelp festzulegen, rufen Sie [EnableHTMLHelp](#enablehtmlhelp). Wenn Sie aufrufen `EnableHTMLHelp`, muss die Anwendung HTMLHelp als seine Hilfe-Anwendung verwenden. Wenn Sie ändern, um die WinHelp verwenden möchten, können Sie aufrufen `SetHelpMode` und *eHelpType* zu `afxWinHelp`.

##  <a name="setregistrykey"></a>  CWinApp::SetRegistryKey

Bewirkt, dass Anwendungseinstellungen in der Registrierung anstelle von INI-Dateien gespeichert werden.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Parameter

*lpszRegistryKey*<br/>
Zeiger auf eine Zeichenfolge, die mit dem Namen des Schlüssels.

*nIDRegistryKey*<br/>
ID des eine Zeichenfolgenressource mit dem Namen des Registrierungsschlüssels.

### <a name="remarks"></a>Hinweise

Diese Funktion legt *M_pszRegistryKey*, wird dann von verwendet die `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, und `WriteProfileString` Memberfunktionen der `CWinApp`. Wenn diese Funktion aufgerufen wurde, wird die Liste der zuletzt verwendeten (MRU)-Dateien auch in der Registrierung gespeichert. Der Registrierungsschlüssel ist in der Regel der Name eines Unternehmens. Es befindet sich in einem Schlüssel mit dem folgenden Format: HKEY_CURRENT_USER\Software\\< Firmenname\>\\< Anwendungsname\>\\< Name des Abschnitts\>\\< Name des\>.

##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery

Bestimmt, ob der Neustart-Manager eine Anwendung wiederhergestellt werden, die unerwartet beendet.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Rückgabewert

"True" gibt an, dass die Anwendung für der Neustart-Manager wiederhergestellt wird. FALSE gibt an, dass der Neustart-Manager nicht der Fall ist.

##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval

Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Abständen zu öffnen.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass der Neustart-Manager speichert Dokumente zu öffnen; FALSE gibt an, dass der Neustart-Manager nicht der Fall ist.

##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart

Bestimmt, ob der Neustart-Manager speichert alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass der Neustart-Manager speichert Dokumente öffnen, wenn die Anwendung neu gestartet wird; FALSE gibt an, dass der Neustart-Manager nicht der Fall ist.

##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager

Bestimmt, ob die Anwendung den Neustart-Manager unterstützt.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass die Anwendung den Neustart-Manager unterstützt wird; FALSE gibt an, dass die Anwendung nicht der Fall ist.

##  <a name="unregister"></a>  CWinApp::Unregister

Hebt die Registrierung aller Dateien, die durch das Anwendungsobjekt registriert.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Die `Unregister` Funktion macht die Registrierung von dem Anwendungsobjekt ausgeführt und die [registrieren](#register) Funktion. Beide Funktionen wird normalerweise durch MFC werden implizit aufgerufen, und werden daher nicht in Ihrem Code angezeigt.

Überschreiben Sie diese Funktion zum Aufheben der Registrierung des benutzerdefinierten Schritte ausführen.

##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes

Rufen Sie diese Memberfunktion zum Aufheben der Registrierung aller Ihrer Anwendung Dokumenttypen mit den Windows-Datei-Manager.

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>  CWinApp::WinHelp

Rufen Sie diese Memberfunktion, um die WinHelp-Anwendung aufzurufen.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Parameter

*dwData*<br/>
Gibt zusätzliche Daten an. Der verwendete Wert hängt vom Wert von der *nCmd* Parameter.

*nCmd*<br/>
Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Auswirkungen auf die *DwData* Parameter finden Sie unter den [WinHelp](/windows/desktop/api/winuser/nf-winuser-winhelpa) Windows-Funktion.

### <a name="remarks"></a>Hinweise

Das Framework ruft auch dieser Funktion können Sie die WinHelp-Anwendung aufzurufen.

Das Framework wird die WinHelp-Anwendung automatisch geschlossen, wenn Ihre Anwendung beendet wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>  CWinApp:: WriteProfileBinary

Rufen Sie diese Memberfunktion zum Schreiben von Binärdaten in den angegebenen Abschnitt der Registrierung von der Anwendung oder. INI-Datei.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts gilt unabhängig; die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.

*lpszEntry*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt.

*pData*<br/>
Verweist auf die Daten geschrieben werden.

*nBytes*<br/>
Enthält die Anzahl der zu schreibenden Bytes.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` , an die CWinApp-Klasse, die zur Veranschaulichung einer Methode abzurufen, die `WriteProfileBinary` und `GetProfileBinary` kann von jeder Funktion in einer MFC-Anwendung verwendet werden.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileBinary](#getprofilebinary).

##  <a name="writeprofileint"></a>  CWinApp:: Writeprofileint

Rufen Sie diese Memberfunktion um den angegebenen Wert in der angegebene Abschnitt von der Anwendung Registrierung zu schreiben oder. INI-Datei.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts gilt unabhängig; die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.

*lpszEntry*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt.

*nWert*<br/>
Enthält den Wert geschrieben werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` , an die CWinApp-Klasse, die zur Veranschaulichung einer Methode abzurufen, die `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, und `GetProfileInt` kann von jeder Funktion in einer MFC-Anwendung verwendet werden.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).

##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString

Rufen Sie diese Memberfunktion, um die angegebene Zeichenfolge in der angegebene Abschnitt von der Anwendung Registrierung zu schreiben oder. INI-Datei.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parameter

*lpszSection*<br/>
Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts gilt unabhängig; die Zeichenfolge kann eine beliebige Kombination von Groß- und Kleinbuchstaben sein.

*lpszEntry*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag nicht im angegebenen Abschnitt vorhanden ist, wird es erstellt. Wenn dieser Parameter NULL ist, im Abschnitt angegeben *LpszSection* wird gelöscht.

*lpszValue*<br/>
Verweist auf die Zeichenfolge, die geschrieben werden. Wenn dieser Parameter NULL ist, wird der Eintrag angegeben, durch die *LpszEntry* Parameter gelöscht wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).

##  <a name="setappid"></a>  CWinApp::SetAppID

Explizit festlegt Anwendungsbenutzer-Modell-ID für die Anwendung ein. Diese Methode sollte aufgerufen werden, bevor eine Benutzeroberfläche für den Benutzer angezeigt wird (der beste Ort ist der Anwendungskonstruktor).

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Parameter

*lpcszAppID*<br/>
Gibt an, die Anwendung Benutzer-Modell-ID.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[CWinThread-Klasse](../../mfc/reference/cwinthread-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[So wird es gemacht: Hinzufügen von Unterstützung für Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)
