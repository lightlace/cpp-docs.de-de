---
title: CWinApp-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CWinApp class
- application objects [C++]
- HINSTANCE
- main object
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 292816c8f753a7b47b563a3fcd0fa336e08acd6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinapp-class"></a>CWinApp-Klasse
Die Basisklasse, von der ein Windows-Anwendungsobjekt abgeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|Erstellt ein `CWinApp`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp:: AddDocTemplate](#adddoctemplate)|Die Anwendung der Liste der verfügbaren Dokumentvorlagen hinzugefügt eine Dokumentvorlage.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Fügt einen Dateinamen zur zuletzt verwendeten Dateiliste (MRU).|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Wird vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|Alle Dokumente schließen|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext.|  
|[CWinApp::DelRegTree](#delregtree)|Löscht einen angegebenen Schlüssel und alle Unterschlüssel.|  
|[CWinApp::DoMessageBox](#domessagebox)|Implementiert [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) für die Anwendung.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|Schaltet den Wartecursor ein und aus.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Ermöglicht der Anwendung `D2D` unterstützen. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Die Anwendung, anstatt WinHelp HTMLHelp implementiert.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Ermöglicht die Interaktion der Taskleiste.|  
|[CWinApp:: ExitInstance](#exitinstance)|Überschreiben Sie zum Bereinigen, wenn Ihre Anwendung beendet wird.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Ruft die Eingabeparameter für die Methode der Anwendung ab.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Gibt die Länge der Zeit, die der Neustart-Manager wartet, bis die Wiederherstellung Rückruffunktion zurückgegeben.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Gibt die Optionen für den Neustart-Manager.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Gibt Schlüssel HKEY_CURRENT_USER\\\RegistryKey\ProfileName "Software".|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Ruft die Daten-Recovery-Handler für diese Instanz der Anwendung ab.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Ruft die Position der ersten Vorlage ab.|  
|[CWinApp::GetHelpMode](#gethelpmode)|Ruft den Typ der Hilfe, die von der Anwendung verwendet.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Ruft die Position einer Dokumentvorlage ab. Rekursiv verwendet kann werden.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Ruft die Standardeinstellungen des Druckers ab.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|Ruft die binären Daten aus einem Eintrag in der Anwendungsverzeichnis ab. INI-Datei.|  
|[CWinApp::GetProfileInt](#getprofileint)|Ruft eine ganze Zahl aus einem Eintrag in der Anwendungsverzeichnis ab. INI-Datei.|  
|[CWinApp::GetProfileString](#getprofilestring)|Ruft eine Zeichenfolge aus einem Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
|[CWinApp::GetSectionKey](#getsectionkey)|Gibt Schlüssel HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection "Software".|  
|[CWinApp::HideApplication](#hideapplication)|Blendet die Anwendung vor dem schließen alle Dokumente aus.|  
|[CWinApp::HtmlHelp](#htmlhelp)|Ruft die `HTMLHelp` -Funktion von Windows.|  
|[CWinApp:: InitInstance](#initinstance)|Außer Kraft setzen Sie, um die Initialisierung des Windows Instanz, z. B. das Erstellen von Windows-Objekte auszuführen.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.|  
|[CWinApp::LoadCursor](#loadcursor)|Lädt eine Cursorressource.|  
|[CWinApp::LoadIcon](#loadicon)|Lädt die Symbolressource.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Lädt ein OEM Windows vordefinierte Cursor, der **OCR_** Konstanten in WINDOWS angeben. H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Lädt ein vordefiniertes Windows OEM-Symbol, das **OIC_** Konstanten in WINDOWS angeben. H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Lädt Windows vordefinierte Cursor, der **IDC_** Konstanten in WINDOWS angeben. H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Lädt ein vordefiniertes Windows-Symbol, die **IDI_** Konstanten in WINDOWS angeben. H.|  
|[CWinApp::OnDDECommand](#onddecommand)|Aufgerufen vom Framework Reaktion zu einem dynamischen Datenaustausch (DDE)-Befehls.|  
|[OnIdle](#onidle)|Überschreiben Sie, um anwendungsspezifische Leerlaufzeit Verarbeitung ausführen.|  
|[CWinApp:: OpenDocumentFile](#opendocumentfile)|Vom Framework aufgerufen wird, ein Dokument aus einer Datei zu öffnen.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|Analysiert einzelner Parameter und Attribute in der Befehlszeile.|  
|[PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten vor dem für die Windows-Funktionen sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung nicht erreichen.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|Behandelt das Befehlszeilenargumente und Flags.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Fängt alle nicht behandelte Ausnahmen, die von der Anwendung und Befehlshandler ausgelöst.|  
|[CWinApp::Register](#register)|Führt die benutzerdefinierte Registrierung.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Registriert die Anwendung den Neustart-Manager.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Bestimmt, ob der Neustart-Manager die Dateien, die geöffnet waren öffnet, wenn die Anwendung unerwartet beendet.|  
|[CWinApp::RestartInstance](#restartinstance)|Verarbeitet einen Neustart der Anwendung durch den Neustart-Manager initiiert.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Bestimmt, ob der Neustart-Manager automatisch gespeicherte Dateien wiederherstellt, wenn sie die Anwendung neu gestartet wird.|  
|[CWinApp:: Run](#run)|Führt die Standardnachrichtenschleife an. Überschreiben Sie, um die Meldungsschleife anpassen.|  
|[CWinApp::RunAutomated](#runautomated)|Befehlszeile für die Anwendung testet die **/Automation** Option. Veraltet. Verwenden Sie stattdessen den Wert im [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) nach dem Aufruf von [ParseCommandLine](#parsecommandline).|  
|[CWinApp::RunEmbedded](#runembedded)|Befehlszeile für die Anwendung testet die **/einbetten** Option. Veraltet. Verwenden Sie stattdessen den Wert im [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) nach dem Aufruf von [ParseCommandLine](#parsecommandline).|  
|[CWinApp::SaveAllModified](#saveallmodified)|Fordert den Benutzer, alle geänderten Dokumente zu speichern.|  
|[CWinApp::SelectPrinter](#selectprinter)|Wählt einen Drucker, die zuvor durch einen Benutzer über ein Druckdialogfeld angegeben.|  
|[CWinApp::SetHelpMode](#sethelpmode)|Legt fest, und initialisiert den Typ der Hilfe, die von der Anwendung verwendet.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Bestimmt, ob der Neustart-Manager eine Anwendung wiederhergestellt, die unerwartet beendet.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Abständen zu öffnen.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Bestimmt, ob der Neustart-Manager automatisch alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Bestimmt, ob die Anwendung vom Neustart-Manager unterstützt.|  
|[CWinApp::Unregister](#unregister)|Alle bekannten registriert werden, indem Sie die Registrierung der `CWinApp` Objekt.|  
|[CWinApp::WinHelp](#winhelp)|Ruft die `WinHelp` -Funktion von Windows.|  
|[CWinApp:: WriteProfileBinary](#writeprofilebinary)|Schreibt binäre Daten auf einen Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
|[CWinApp:: Writeprofileint](#writeprofileint)|Schreibt eine ganze Zahl mit einem Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|Schreibt eine Zeichenfolge in einen Eintrag in der Anwendungsverzeichnis. INI-Datei.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Ermöglicht dem Benutzer um Datendateien vom Datei-Manager von Windows zu öffnen.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Lädt Standard. INI-Datei und ermöglicht die MRU-Datei-Funktion.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|UMSCHALT + F1-Hilfe in der Anwendung verarbeitet werden.|  
|[CWinApp::OnFileNew](#onfilenew)|Implementiert die `ID_FILE_NEW` Befehl.|  
|[CWinApp::OnFileOpen](#onfileopen)|Implementiert die `ID_FILE_OPEN` Befehl.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Implementiert die `ID_FILE_PRINT_SETUP` Befehl.|  
|[CWinApp::OnHelp](#onhelp)|Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|Verarbeitet die Befehle `ID_HELP_FINDER` und `ID_DEFAULT_HELP`.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|Verarbeitet den Befehl `ID_HELP_INDEX` und stellt ein standardmäßiges Hilfethema bereit.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|Verarbeitet den Befehl `ID_HELP_USING`.|  
|[CWinApp:: RegisterShellFileTypes](#registershellfiletypes)|Registriert die Dokumenttypen alle für die Anwendung mit dem Windows-Datei-Manager.|  
|[CWinApp::SetAppID](#setappid)|Explizit festlegt Modell Benutzer-ID für die Anwendung. Diese Methode sollte aufgerufen werden, bevor die Benutzer keine Benutzeroberfläche angezeigt wird (am besten ist der Anwendungskonstruktor).|  
|[CWinApp::SetRegistryKey](#setregistrykey)|Bewirkt, dass Einstellungen in der Registrierung gespeichert werden. INI-Dateien.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Hebt die Registrierung Dokumenttypen für alle für die Anwendung mit dem Windows-Datei-Manager.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Gibt an, ob der Benutzer im Kontext Hilfemodus (i. d. r. mit UMSCHALT + F1 aufgerufen).|  
|[CWinApp::m_eHelpType](#m_ehelptype)|Gibt den Typ der Hilfe, die von der Anwendung verwendet.|  
|[CWinApp::m_hInstance](#m_hinstance)|Identifiziert die aktuelle Instanz der Anwendung.|  
|[CWinApp:: M_lpcmdline](#m_lpcmdline)|Zeigt auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Gibt an, wie das Fenster anfänglich angezeigt werden.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server direkt aktiv ist.|  
|[CWinApp::m_pszAppID](#m_pszappid)|Anwendungsbenutzer-ID-Modell|  
|[CWinApp::m_pszAppName](#m_pszappname)|Gibt den Namen der Anwendung an.|  
|[CWinApp::m_pszExeName](#m_pszexename)|Der Modulname der Anwendung.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Der Pfad zu der Anwendung Hilfedatei.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Der Anwendungsverzeichnis zugeordnet ist. INI-Dateiname.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Dient zum Bestimmen des vollständigen Registrierungsschlüssels um Anwendungseinstellungen Profil zu speichern.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Flags, die das Verhalten des Neustart-Managers bestimmt.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Die Zeitdauer in Millisekunden zwischen speichert.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Ein Zeiger auf die Daten-Recovery-Handler für die Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Anwendungsobjekt stellt Memberfunktionen zum Initialisieren der Anwendung (und jede Instanz) und für die Ausführung der Anwendung.  
  
 Jede Anwendung, die die Microsoft Foundation-Klassen kann nur ein abgeleitetes Objekt enthalten `CWinApp`. Dieses Objekt wird erstellt, wenn andere globale C++-Objekte erstellt werden und ist bereits verfügbar, wenn Windows ruft die `WinMain` -Funktion, die von der Microsoft Foundation Class-Bibliothek bereitgestellt wird. Deklarieren der abgeleiteten `CWinApp` Objekt auf globaler Ebene.  
  
 Beim Ableiten einer Anwendungsklasse von `CWinApp`, überschreiben die [InitInstance](#initinstance) Member-Funktion, um Ihre Anwendung im Hauptfenster-Objekt zu erstellen.  
  
 Zusätzlich zu den `CWinApp` Memberfunktionen, die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen für den Zugriff auf Ihre `CWinApp` Objekt und andere globale Informationen:  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) erhält einen Zeiger auf die `CWinApp` Objekt.  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) gibt einen Handle für die aktuelle Anwendungsinstanz.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) gibt einen Handle für die Ressourcen der Anwendung.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) erhält einen Zeiger auf eine Zeichenfolge, die den Namen der Anwendung enthält. Alternativ ist einen Zeiger auf die `CWinApp` -Objekts `m_pszExeName` auf den Namen der Anwendung zu erhalten.  
  
 Finden Sie unter [CWinApp: die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md) Weitere Informationen über die `CWinApp` -Klasse, einschließlich einer Übersicht über die folgenden:  
  
- `CWinApp`-Code geschrieben wurde, indem Sie den Assistenten zum abgeleitet.  
  
- `CWinApp`die Rolle in der Ausführungsreihenfolge der Anwendung.  
  
- `CWinApp`einer Standardeinstellung Memberimplementierungen-Funktion.  
  
- `CWinApp`der Schlüssel Overridables.  
  
 Die **M_hPrevInstance** -Datenmember nicht mehr vorhanden ist. Informationen zum Erkennen von einer vorherigen Instanz der `CWinApp`, finden Sie unter "Vorgehensweise Identifizieren einer vorherigen Instanz von eine Anwendung" (KB106385) Knowledge Base-Artikel unter [http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="adddoctemplate"></a>CWinApp:: AddDocTemplate  
 Rufen Sie diese Memberfunktion, um die Anwendung verwaltet die Liste der verfügbaren Vorlagen eine Dokumentvorlage hinzuzufügen.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `pTemplate`  
 Ein Zeiger auf die `CDocTemplate` hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten alle Dokumentvorlagen für eine Anwendung vor dem Aufruf von hinzufügen [RegisterShellFileTypes](#registershellfiletypes).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#35;](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 Rufen Sie diese Memberfunktion hinzufügen `lpszPathName` der Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Der Pfad der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [LoadStdProfileSettings](#loadstdprofilesettings) Memberfunktion, die die aktuelle Liste der zuletzt verwendeten Datei zu laden, bevor Sie diese Member-Funktion verwenden.  
  
 Das Framework ruft diese Member-Funktion beim Öffnen einer Datei oder den Befehl "Speichern unter führt" eine Datei mit einem neuen Namen speichern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&36;](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 Wird vom Framework aufgerufen, wenn die Anwendung unerwartet beendet wird.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpvParam`  
 Für zukünftige Verwendung reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn diese Methode erfolgreich ist; ungleich NULL, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung den Neustart-Manager unterstützt, ruft das Framework diese Funktion, wenn die Anwendung unerwartet beendet wird.  
  
 Die standardmäßige Implementierung des `ApplicationRecoveryCallback` verwendet die `CDataRecoveryHandler` um die Liste der aktuell geöffneten Dokumente in der Registrierung speichern. Diese Methode führt keine automatische Speicherung alle Dateien.  
  
 Um das Verhalten anpassen möchten, überschreiben Sie diese Funktion in einer abgeleiteten [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) oder Ihre eigene Anwendung Recovery-Methode als Parameter übergeben [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
##  <a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 Rufen Sie diese Memberfunktion zum Schließen aller geöffneten Dokumente vor dem Beenden.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parameter  
 `bEndSession`  
 Gibt an, ob die Windows-Sitzung beendet wird. Es ist **TRUE** wird die Sitzung beendet wird andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [HideApplication](#hideapplication) vor dem Aufruf von `CloseAllDocuments`.  
  
##  <a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 Rufen Sie diese Memberfunktion auf einen Drucker-Gerätekontext (DC) über den ausgewählten Drucker erstellen.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Ein Verweis auf einen Drucker-Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Drucker-Gerätekontext erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `CreatePrinterDC`Initialisiert den Gerätekontext, den Sie in eine als Verweis übergeben, sodass Sie es zum Drucken verwenden können.  
  
 Wenn die Funktion erfolgreich ist, wenn Sie den Druckvorgang abgeschlossen haben, müssen Sie den Gerätekontext zerstören. Den Destruktor können die [CDC](../../mfc/reference/cdc-class.md) Objekt dafür oder können Sie dies tun explizit durch Aufrufen von [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).  
  
##  <a name="cwinapp"></a>CWinApp::CWinApp  
 Erstellt eine `CWinApp` Objekt auf und übergibt `lpszAppName` als den Namen der Anwendung gespeichert werden.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszAppName`  
 Eine auf Null endende Zeichenfolge, die den Namen der Anwendung enthält, den Windows verwendet. Wenn dieses Argument nicht angegeben wird oder **NULL**, `CWinApp` verwendet die Zeichenfolgenressource **AFX_IDS_APP_TITLE** oder den Dateinamen der ausführbaren Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten ein globales Objekt erstellen Ihrer `CWinApp`-abgeleiteten Klasse. Stehen Ihnen nur ein `CWinApp` Objekt in der Anwendung. Der Konstruktor speichert einen Zeiger auf die `CWinApp` Objekt, damit `WinMain` können Funktionen aufrufen, Member des Objekts zu initialisieren und die Anwendung auszuführen.  
  
##  <a name="delregtree"></a>CWinApp::DelRegTree  
 Löscht einen bestimmten Registrierungsschlüssel und alle Unterschlüssel.  
  
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
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den angegebenen Schlüssel und dessen Unterschlüssel löschen.  
  
##  <a name="domessagebox"></a>CWinApp::DoMessageBox  
 Das Framework ruft diese Member-Funktion, um ein Meldungsfeld für die globale Funktion implementieren [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPrompt*  
 Adresse des Texts in der MessageBox.  
  
 `nType`  
 Das Meldungsfeld [Stil](../../mfc/reference/message-box-styles.md).  
  
 `nIDPrompt`  
 Ein Index in eine Zeichenfolge der Hilfe-Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die gleichen Werte wie `AfxMessageBox`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht diese Memberfunktion, um ein Meldungsfeld geöffnet. Verwenden Sie `AfxMessageBox` stattdessen.  
  
 Überschreiben Sie diese Memberfunktion zum Anpassen Ihrer Verarbeitung anwendungsweite `AfxMessageBox` aufrufen.  
  
##  <a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 Diese Memberfunktion aufgerufen wird, vom Framework implementieren [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nCode`  
 Wenn dieser Parameter 1 ist, wird ein Wartecursor angezeigt. Bei 0 wird der Wartecursor wiederhergestellt, ohne den Verweiszähler erhöht. Wenn –&1; ist, wird der Wartecursor beendet.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird ein Sanduhrcursor implementiert. `DoWaitCursor`verwaltet einen Verweiszähler. Wenn positiv ist, wird der Sanduhrcursor angezeigt.  
  
 Obwohl Sie normalerweise nicht aufrufen würde `DoWaitCursor` direkt, Sie können außer Kraft setzen diese Member-Funktion, um den Wartecursor ändern oder zusätzliche Verarbeitung während der Wartecursor angezeigt wird.  
  
 Verwenden Sie für eine einfachere, übersichtlichere Möglichkeit, einen Wartecursor zu implementieren, `CWaitCursor`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#37;](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
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
 Gibt TRUE zurück, wenn D2D-Unterstützung aktiviert -, andernfalls FALSE wurde  
  
##  <a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 Rufen Sie diese Memberfunktion aus innerhalb des Konstruktors der Ihre `CWinApp`-abgeleitete Klasse HTMLHelp Hilfestellung bei der Anwendung zu verwenden.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 Rufen Sie diese Funktion in der Regel die `InitInstance` außer Kraft setzen, Ihre Anwendung Benutzern ermöglichen, Datendateien zu öffnen, wenn sie die Dateien aus der Datei-Manager in Windows doppelklicken.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `RegisterShellFileTypes` Member-Funktion in Verbindung mit dieser Funktion, oder geben Sie ein. REG-Datei mit Ihrer Anwendung für die manuelle Registrierung von Dokumenttypen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#38;](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
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
 Vom Framework aufgerufen wird, innerhalb der **ausführen** Member-Funktion, um diese Instanz der Anwendung zu beenden.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Code der Anwendung beenden; 0 gibt keine Fehler an, und Werte größer als 0 Fehler an. Dieser Wert dient als Rückgabewert von `WinMain`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht diese Memberfunktion überall aber noch innerhalb der **ausführen** Member-Funktion.  
  
 Die standardmäßige Implementierung dieser Funktion schreibt Framework-Optionen in der Anwendungsverzeichnis. INI-Datei. Überschreiben Sie diese Funktion zum Bereinigen, wenn Ihre Anwendung beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&39;](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 Ruft die Eingabeparameter für die Methode der Anwendung ab.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standard-Eingabeparameter für die Anwendung Wiederherstellungsmethode.  
  
### <a name="remarks"></a>Hinweise  
 Gibt das Standardverhalten dieser Funktion `NULL`.  
  
 Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
##  <a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 Gibt die Länge der Zeit, die der Neustart-Manager wartet, bis die Wiederherstellung Rückruffunktion zurückgegeben.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeitdauer in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung, die für den Neustart-Manager beendet unerwartet registriert ist, wird die Anwendung versucht, die geöffneten Dokumente speichern und ruft die Rückruffunktion Wiederherstellung. Ist die Wiederherstellung Standardrückruffunktion [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
 Die Länge der Zeit, die das Framework für die Wiederherstellung Rückruffunktion zurückzugebenden wartet ist das pingintervall. Sie können das pingintervall anpassen, indem Sie überschreiben `CWinApp::GetApplicationRecoveryPingInterval` oder durch Angeben eines benutzerdefinierten Werts zu `RegisterWithRestartManager`.  
  
##  <a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 Gibt die Optionen für den Neustart-Manager.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Flags für den Neustart-Manager. Die standardmäßige Implementierung gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Flags für den Neustart-Manager wirken sich nicht mit der Standardimplementierung. Sie werden für die zukünftige Verwendung bereitgestellt.  
  
 Beim Registrieren der Anwendung mit den Neustart-Manager verwenden, legen Sie die Flags [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
 Die möglichen Werte für den Neustart-Manager-Flags sind wie folgt:  
  
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
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 ANWENDUNGSTASTE, wenn die Funktion erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 Ruft die Daten-Recovery-Handler für diese Instanz der Anwendung ab.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Daten-Recovery-Handler für diese Instanz der Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Jede Anwendung, die den Neustart-Manager wird verwendet, benötigen Sie eine Instanz der [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Diese Klasse ist verantwortlich für die Überwachung von geöffnete Dokumente und die automatische Speicherung von Dateien. Das Verhalten der `CDataRecoveryHandler` hängt von der Konfiguration des Neustart-Managers. Weitere Informationen finden Sie unter [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
 Diese Methode gibt `NULL` auf Betriebssystemen vor [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Der Neustart-Manager wird nicht unter Betriebssystemen vor [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Wenn die Anwendung noch nicht über einen Daten-Recovery-Handler ist, wird diese Methode erstellt und gibt einen Zeiger darauf zurück.  
  
##  <a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 Ruft die Position der ersten Dokumentvorlage in der Anwendung.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** Wenn die Liste leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der **POSITION** zurückgegebene Wert in einem Aufruf von [GetNextDocTemplate](#getnextdoctemplate) zum Abrufen der ersten [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.  
  
##  <a name="gethelpmode"></a>CWinApp::GetHelpMode  
 Ruft den Typ der Hilfe, die von der Anwendung verwendet.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Hilfe-Typ, der von der Anwendung verwendet wird. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) Weitere Informationen.  
  
##  <a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 Ruft die Dokumentvorlage identifizierten `pos`, legt dann `pos` an der **POSITION** Wert.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** von einem vorherigen Aufruf zurückgegebene Wert `GetNextDocTemplate` oder [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Der Wert wird durch diesen Aufruf an die nächste Position aktualisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNextDocTemplate` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetFirstDocTemplatePosition`.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert ist ungültig. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Die abgerufenen Dokumentvorlage ist die letzte verfügbar ist, klicken Sie dann den neuen Wert der `pos` auf festgelegt ist **NULL**.  
  
##  <a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 Rufen Sie diese Memberfunktion, um einen Drucker-Gerätekontext für den Druck vorzubereiten.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>Parameter  
 *pPrintDlg*  
 Ein Zeiger auf eine [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ruft den aktuellen Druckerstandardeinstellungen von Windows ab. INI-Datei als erforderlich oder die letzten Konfiguration durch den Benutzer in der Print-Installation festgelegt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#40;](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="getprofilebinary"></a>CWinApp::GetProfileBinary  
 Rufen Sie diese Memberfunktion zum Abrufen von Binärdaten aus einem Eintrag in einem angegebenen Abschnitt der Registrierung der Anwendung oder. INI-Datei.  
  
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
 Zeigt auf einen Zeiger, der die Adresse der Daten zu erhalten.  
  
 *pBytes*  
 Verweist auf ein UINT, die die Größe der Daten (in Byte) erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist also keine Groß-/Kleinschreibung beachten, die Zeichenfolgen in der *LpszSection* und *LpszEntry* Parameter in Fall abweichen können.  
  
> [!NOTE]
> **GetProfileBinary** reserviert einen Puffer und gibt dessen Adresse in \* *PpData*. Der Aufrufer ist verantwortlich für die Freigabe der Puffer mit **delete []**.  
  
> [!IMPORTANT]
>  Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#41;](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 Ein zusätzliches Beispiel finden Sie unter [CWinApp:: WriteProfileBinary](#writeprofilebinary).  
  
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
 [!code-cpp[NVC_MFCWindowing&#42;](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 Ein zusätzliches Beispiel finden Sie unter [CWinApp:: Writeprofileint](#writeprofileint).  
  
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
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, dessen Zeichenfolge abgerufen werden soll. Dieser Wert darf nicht sein **NULL**.  
  
 `lpszDefault`  
 Verweist auf den Standard-Zeichenfolgenwert für den angegebenen Eintrag aus, wenn der Eintrag in der Initialisierungsdatei gefunden werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist die Zeichenfolge, aus der Anwendungsverzeichnis. INI-Datei oder `lpszDefault` , wenn die Zeichenfolge nicht gefunden werden kann. Ist die maximale Zeichenfolgenlänge von Framework unterstützten `_MAX_PATH`. Wenn `lpszDefault` ist **NULL**, der Rückgabewert ist eine leere Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Die von dieser Funktion zurückgegebenen Daten enden nicht notwendigerweise auf NULL, und der Aufrufer muss die Validierung ausführen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
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
 Der Name des Schlüssels, der abgerufen werden.  
  
 `pTM`  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Abschnitt-Schlüssel, wenn die Funktion erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideapplication"></a>CWinApp::HideApplication  
 Rufen Sie diese Memberfunktion zum Ausblenden einer Anwendung vor dem Schließen des geöffneten Dokumente.  
  
```  
void HideApplication();
```  
  
##  <a name="htmlhelp"></a>CWinApp::HtmlHelp  
 Rufen Sie diese Memberfunktion zum Aufrufen der HTMLHelp-Anwendung.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Gibt zusätzliche Daten an. Der verwendete Wert hängt vom Wert von der `nCmd` Parameter.  
  
 `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Auswirkung auf die der `dwData` -Parameter finden Sie unter der `uCommand` Parameter beschrieben, die in über die HTMLHelp-API-Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch diese Funktion, um die Anwendung HTMLHelp aufrufen.  
  
 Das Framework wird die HTMLHelp-Anwendung automatisch geschlossen, wenn die Anwendung beendet wird.  
  
##  <a name="initinstance"></a>CWinApp:: InitInstance  
 Windows ermöglicht, mehrere Kopien desselben Programms zum gleichen Zeitpunkt ausgeführt wird.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Initialisieren der Anwendung ist im Prinzip in zwei Abschnitte unterteilt: einmalige anwendungsinitialisierung die Beendigung der ersten Ausführung des Programms und Initialisierung von Instanzen, die jeweils ausgeführt wird eine Kopie der Anwendung ausgeführt wird, einschließlich beim ersten Mal. Implementierung des Frameworks `WinMain` ruft diese Funktion auf.  
  
 Überschreiben Sie `InitInstance` initialisiert jede neue Instanz der Anwendung unter Windows ausgeführt werden. Überschreiben Sie in der Regel `InitInstance` das Hauptfenster-Objekt erstellen und Festlegen der `CWinThread::m_pMainWnd` -Datenmember auf dieses Fenster zeigen. Weitere Informationen zum Überschreiben dieser Memberfunktion finden Sie unter [CWinApp: die Anwendungsklasse](../../mfc/cwinapp-the-application-class.md).  
  
> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in Ihrer `InitInstance` außer Kraft setzen, geben Sie `COINIT_APARTMENTTHREADED` (statt `COINIT_MULTITHREADED`). Weitere Informationen finden Sie unter PRB: MFC-Anwendung reagiert nicht mehr, wenn Sie die Anwendung als eine Multithread-Apartment initialisieren (828643) am initialisieren [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView&#9;](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Erfahren Sie, ob Windows 7-Taskleiste Interaktion aktiviert ist.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn `EnableTaskbarInteraction` aufgerufen wurde und das Betriebssystem Windows 7 oder höher ist.  
  
### <a name="remarks"></a>Hinweise  
 Taskleiste Interaktion bedeutet, dass MDI-Anwendung den Inhalt des untergeordneten MDI-Objekte in separaten Miniaturansichten mit Registerkarten, die angezeigt werden angezeigt, wenn der Mauszeiger auf die Taskleistenschaltfläche für die Anwendung.  
  
##  <a name="loadcursor"></a>CWinApp::LoadCursor  
 Lädt die Cursorressource mit dem Namen `lpszResourceName` oder vom angegebenen `nIDResource` aus der aktuellen ausführbaren Datei.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  ```  
  
### Parameters  
 `lpszResourceName`  
 Points to a null-terminated string that contains the name of the cursor resource. You can use a `CString` for this argument.  
  
 `nIDResource`  
 ID of the cursor resource. For a list of resources, see [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 A handle to a cursor if successful; otherwise **NULL**.  
  
### Remarks  
 `LoadCursor` loads the cursor into memory only if it has not been previously loaded; otherwise, it retrieves a handle of the existing resource.  
  
 Use the [LoadStandardCursor](#loadstandardcursor) or [LoadOEMCursor](#loadoemcursor) member function to access the predefined Windows cursors.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Loads the icon resource named by `lpszResourceName` or specified by `nIDResource` from the executable file.  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;  ```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Symbolressource enthält. Sie können auch eine `CString` für dieses Argument.  
  
 `nIDResource`  
 ID-Nummer der Symbolressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 `LoadIcon`Lädt das Symbol, nur, wenn es nicht bereits geladen wurde. Andernfalls wird ein Handle für die vorhandene Ressource.  
  
 Sie können die [LoadStandardIcon](#loadstandardicon) oder [LoadOEMIcon](#loadoemicon) Memberfunktion auf vordefinierte Windows-Symbole.  
  
> [!NOTE]
>  Diese Memberfunktion Ruft die Win32-API-Funktion [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), laden die nur ein Symbol, dessen Größe entspricht, der **SM_CXICON zugeordnet** und **SM_CYICON zugeordnet** System metrischen Werte.  
  
##  <a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 Lädt Windows vordefinierte Cursor-Ressource, die durch angegebene `nIDCursor`.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCursor`  
 Ein **OCR_** manifest Konstante Bezeichner, der einen vordefinierten Windows Cursor gibt. Sie benötigen **#define OEMRESOURCE** vor **#include \<afxwin.h >** für den Zugriff auf die **OCR_** Konstanten in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadOEMCursor` oder [LoadStandardCursor](#loadstandardcursor) Memberfunktion, die die vordefinierten Windows-Cursors zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#45;](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#46;](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 Lädt Windows vordefinierte Symbolressource angegebenen `nIDIcon`.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDIcon`  
 Ein **OIC_** manifest Konstante Bezeichner, der ein vordefiniertes Windows-Symbol gibt. Sie benötigen **#define OEMRESOURCE** vor **#include \<afxwin.h >** für den Zugriff auf die **OIC_** Konstanten in WINDOWS. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadOEMIcon` oder [LoadStandardIcon](#loadstandardicon) Memberfunktion auf vordefinierte Windows-Symbole.  
  
##  <a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 Lädt Windows vordefinierte Cursor-Ressource, die `lpszCursorName` angibt.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszCursorName`  
 Ein **IDC_** manifest Konstante Bezeichner, der einen vordefinierten Windows Cursor gibt. Diese Bezeichner werden in WINDOWS definiert. H. Die folgende Liste zeigt die möglichen vordefinierte Werte und die Bedeutung für `lpszCursorName`:  
  
- **IDC_ARROW** Standardpfeilcursor  
  
- **IDC_IBEAM** Standard-Text-Einfügemarke  
  
- **IDC_WAIT** Sanduhr Cursor verwendet, wenn Windows eine zeitaufwändige Aufgabe ausführt  
  
- **IDC_CROSS** Fadenkreuz-Cursor für die Auswahl  
  
- **IDC_UPARROW** Pfeil nach oben  
  
- **IDC_SIZE** veraltet und wird nicht unterstützt; **IDC_SIZEALL**  
  
- **IDC_SIZEALL** ein Pfeil mit vier Spitzen. Der Cursor zu verwenden, um die Größe eines Fensters ändern.  
  
- **IDC_ICON** veraltet und nicht unterstützt. Verwendung **IDC_ARROW**.  
  
- **IDC_SIZENWSE** Doppelpfeil mit endet am oben links und rechts unten  
  
- **IDC_SIZENESW** Pfeil am oberen rechten und unteren linken Ecke endet mit zwei Spitzen  
  
- **IDC_SIZEWE** horizontaler Pfeil mit zwei Spitzen  
  
- **IDC_SIZENS** Senkrechter Pfeil mit zwei Spitzen  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf einen Cursor, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadStandardCursor` oder [LoadOEMCursor](#loadoemcursor) Memberfunktion, die die vordefinierten Windows-Cursors zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#47;](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 Lädt Windows vordefinierte Symbolressource, die `lpszIconName` angibt.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIconName`  
 Ein manifest Konstante Bezeichner, der ein vordefiniertes Windows-Symbol gibt. Diese Bezeichner werden in WINDOWS definiert. H. Eine Liste mit den möglichen Werten und ihren Beschreibungen finden Sie in der *LpIconName* -Parameter in [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `LoadStandardIcon` oder [LoadOEMIcon](#loadoemicon) Memberfunktion auf vordefinierte Windows-Symbole.  
  
##  <a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings  
 Rufen Sie diese Memberfunktion innerhalb der [InitInstance](#initinstance) Member-Funktion aktivieren und die Liste der zuletzt verwendeten (MRU)-Dateien laden und Status zuletzt in der Vorschau anzeigen.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxMRU`  
 Die Anzahl der zuletzt verwendeten Dateien nachverfolgen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nMaxMRU` gleich 0 ist, werden keine MRU-Liste beibehalten.  
  
##  <a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **True,** ist die Anwendung im Kontext Hilfemodus (konventionell mit UMSCHALT + F1 aufgerufen); andernfalls **FALSE**.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Im Kontext des Hilfemodus der Cursor wird ein Fragezeichen, und der Benutzer über den Bildschirm bewegen. Überprüfen Sie dieses Flag, wenn Sie besondere Behandlung in den Hilfemodus implementieren möchten. `m_bHelpMode`ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 Flags, die das Verhalten des Neustart-Managers bestimmt.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie zum Aktivieren des Neustart-Managers `m_dwRestartManagerSupportFlags` auf das gewünschte Verhalten. Die folgende Tabelle zeigt die Flags, die verfügbar sind.  
  
|||  
|-|-|  
|Flag|Beschreibung|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|Die Anwendung registriert ist, mithilfe von [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Der Neustart-Manager ist verantwortlich für die Anwendung neu, wenn es unerwartet beendet wird.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|Die Anwendung wird mit den Neustart-Manager registriert und der Neustart-Manager Ruft die Rückruffunktion Wiederherstellung beim Neustart der Anwendung. Ist die Wiederherstellung Standardrückruffunktion [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|Automatisches Speichern aktiviert ist und der Neustart-Manager automatisch alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|Automatisches Speichern aktiviert ist und der Neustart-Manager speichert alle Dokumente in regelmäßigen Intervallen öffnen. Das Intervall wird definiert, indem [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|Der Neustart-Manager wird vorher geöffnete Dokumente nach dem Neustart der Anwendung ein unerwartetes Beenden des Programms geöffnet. Die [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md) behandelt, die Liste der geöffneten Dokumente speichern und wiederherstellen.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|Der Neustart-Manager fordert den Benutzer automatisch gespeicherte Dateien wiederherstellen nach einem Neustart der Anwendung. Die `CDataRecoveryHandler` Klasse fragt den Benutzer.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|Die Gesamtmenge der `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, und `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 Der Typ der Datenmember ist der Enumerationstyp **AFX_HELP_TYPE**, definiert in der `CWinApp` Klasse.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die **AFX_HELP_TYPE** Enumeration ist wie folgt definiert:  
  
 `enum AFX_HELP_TYPE`  
  
 `{`  
  
 `afxWinHelp = 0,`  
  
 `afxHTMLHelp = 1`  
  
 `};`  
  
-   Rufen Sie zum Festlegen der Anwendungshilfe HTML-Hilfe [SetHelpMode](#sethelpmode) und geben Sie **AfxHTMLHelp**.  
  
-   Rufen Sie zum Festlegen der Anwendung dienen dem WinHelp `SetHelpMode` und geben Sie **AfxWinHelp**.  
  
##  <a name="m_hinstance"></a>CWinApp::m_hInstance  
 Entspricht der `hInstance` Parameter übergeben von Windows für `WinMain`.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der `m_hInstance` -Datenmember ist ein Handle für die aktuelle Instanz der Anwendung unter Windows ausgeführt wird. Dies ist die globale Funktion zurückgegebene [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance`ist eine öffentliche Variable des Typs `HINSTANCE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#55;](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>CWinApp:: M_lpcmdline  
 Entspricht der `lpCmdLine` Parameter übergeben von Windows für `WinMain`.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Hinweise  
 Zeigt auf eine auf Null endende Zeichenfolge, die die Befehlszeile für die Anwendung angibt. Verwendung `m_lpCmdLine` auf Befehlszeilenargumente zuzugreifen, vom Benutzer eingegeben werden, wenn die Anwendung gestartet wurde. `m_lpCmdLine`ist eine öffentliche Variable des Typs `LPTSTR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 Die Zeitdauer in Millisekunden zwischen speichert.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Neustart-Manager Autosave geöffnete Dokumente in festgelegten Intervallen konfigurieren. Wenn Ihre Anwendung keine Autosave-Dateien, hat dieser Parameter keine Auswirkung.  
  
##  <a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 Entspricht der `nCmdShow` Parameter übergeben von Windows für `WinMain`.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie `m_nCmdShow` als Argument beim Aufrufen [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) für das Hauptfenster der Anwendung. `m_nCmdShow`ist eine öffentliche Variable des Typs `int`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#56;](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd  
 Verwenden Sie dieses Datenelement, um einen Zeiger auf das Hauptfenster der OLE-Container-Anwendung zu speichern, die OLE-Server-Anwendung direkte aktiviert hat.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Datenmember ist **NULL**, die Anwendung ist nicht direkt aktiviert.  
  
 Wenn das Rahmenfenster von einer OLE-Container-Anwendung aktiviert ist, setzt das Framework diese Membervariable.  
  
##  <a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 Ein Zeiger auf die Daten-Recovery-Handler für die Anwendung.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Hinweise  
 Daten-Recovery-Handler einer Anwendung überwacht, geöffneten Dokumenten und speichert sie. Das Framework verwendet Daten Recovery-Handler automatisch gespeicherte Dateien wiederherstellen, wenn eine Anwendung neu gestartet wird, nachdem er unerwartet beendet wird. Weitere Informationen finden Sie unter [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
##  <a name="m_pszappname"></a>CWinApp::m_pszAppName  
 Gibt den Namen der Anwendung an.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Name der Anwendung kann von den übergebenen Parameter stammen die [CWinApp](#cwinapp) -Konstruktor oder, falls nicht angegeben, auf die Ressourcenzeichenfolge mit der ID **AFX_IDS_APP_TITLE**. Wenn der Anwendungsname in der Ressource nicht gefunden wird, erfolgt von des Programms. EXE-Dateiname.  
  
 Die globale Funktion zurückgegebene [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuweisen `m_pszAppName`, muss dynamisch auf dem Heap reserviert. Die `CWinApp` Destruktoraufrufe **freien**() mit diesem Zeiger. Viele soll die `_tcsdup`()-Laufzeitbibliothek Funktion der zuordnen. Darüber hinaus freigeben Sie den Speicher, die Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#57;](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#65;](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>CWinApp::m_pszExeName  
 Enthält den Namen der ausführbaren Datei der Anwendung ohne Erweiterung.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [M_pszAppName](#m_pszappname), dieser Name darf keine Leerzeichen enthalten. `m_pszExeName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuweisen `m_pszExeName`, muss dynamisch auf dem Heap reserviert. Die `CWinApp` Destruktoraufrufe **freien**() mit diesem Zeiger. Viele soll die `_tcsdup`()-Laufzeitbibliothek Funktion der zuordnen. Darüber hinaus freigeben Sie den Speicher, die Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#58;](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 Enthält den Pfad zur Hilfedatei für die Anwendung.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung initialisiert das Framework `m_pszHelpFilePath` auf den Namen der Anwendung ". HLP"angefügt. Legen Sie zum Ändern der Name der Hilfedatei `m_pszHelpFilePath` , zeigen Sie auf eine Zeichenfolge, die den vollständigen Namen der gewünschten Hilfedatei enthält. Eine bequeme Möglichkeit hierzu ist in der Anwendungsverzeichnis [InitInstance](#initinstance) Funktion. `m_pszHelpFilePath`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuweisen `m_pszHelpFilePath`, muss dynamisch auf dem Heap reserviert. Die `CWinApp` Destruktoraufrufe **freien**() mit diesem Zeiger. Viele soll die `_tcsdup`()-Laufzeitbibliothek Funktion der zuordnen. Darüber hinaus freigeben Sie den Speicher, die Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#59;](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 Enthält den Namen der Anwendung. INI-Datei.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_pszProfileName`ist eine öffentliche Variable des Typs **const Char\***.  
  
> [!NOTE]
>  Wenn Sie einen Wert zuweisen `m_pszProfileName`, muss dynamisch auf dem Heap reserviert. Die `CWinApp` Destruktoraufrufe **freien**() mit diesem Zeiger. Viele soll die `_tcsdup`()-Laufzeitbibliothek Funktion der zuordnen. Darüber hinaus freigeben Sie den Speicher, die Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&60;](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 Verwendet, um zu bestimmen, in der Registrierung oder der INI-Datei, die Anwendung profileinstellungen gespeichert werden.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Datenelement wird normalerweise als schreibgeschützt behandelt.  
  
-   Der Wert wird an einem Registrierungsschlüssel gespeichert. Der Name für die anwendungseinstellung wird angefügt, auf den folgenden Registrierungsschlüssel: HKEY_CURRENT_USER/Software/LocalAppWizard-generierten /.  
  
 Wenn Sie einen Wert zuweisen `m_pszRegistryKey`, muss dynamisch auf dem Heap reserviert. Die `CWinApp` Destruktoraufrufe **freien**() mit diesem Zeiger. Viele soll die `_tcsdup`()-Laufzeitbibliothek Funktion der zuordnen. Darüber hinaus freigeben Sie den Speicher, die Zeiger auf den aktuellen zugeordnet sind, bevor Sie einen neuen Wert zuweisen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#61;](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>CWinApp::m_pszAppID  
 Anwendungsbenutzer-ID-Modell  
  
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
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` Anweisung, um Ihre `CWinApp` Klasse meldungszuordnung und Eintrags in einer Zugriffstastentabelle, in der Regel UMSCHALT + F1 drücken, aktivieren Sie diese Memberfunktion hinzufügen.  
  
 `OnContextHelp`versetzt die Anwendung in den Hilfemodus. Wechselt der Cursor zu einem Pfeil und ein Fragezeichen, und der Benutzer können dann den Mauszeiger und drücken Sie die linke Maustaste gedrückt, um ein Dialogfeld, Fenster, Menüs oder Befehlsschaltfläche auszuwählen. Diese Memberfunktion Ruft den Hilfekontext für das Objekt unter dem Cursor und ruft die Windows-Funktion WinHelp, Hilfe-Kontext.  
  
##  <a name="onddecommand"></a>CWinApp::OnDDECommand  
 Vom Framework aufgerufen wird, wenn das Hauptrahmenfenster eine DDE empfängt Nachrichten führen.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszCommand*  
 Zeigt auf eine DDE-Befehl-Zeichenfolge, die von der Anwendung empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Befehl behandelt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft, ob der Befehl eine Anforderung zum Öffnen eines Dokuments ist, und wenn dies der Fall ist, das angegebene Dokument öffnet. Den Datei-Manager von Windows sendet z. B. DDE-Befehlszeichenfolgen in der Regel, wenn der Benutzer eine Datei doppelklickt. Überschreiben Sie diese Funktion in anderen DDE behandeln führen Befehle aus, wie z. B. den Befehl zum Drucken.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#48;](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>CWinApp::OnFileNew  
 Implementiert die `ID_FILE_NEW` Befehl.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_FILE_NEW, OnFileNew )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn aktiviert, behandelt diese Funktion Ausführung des Befehls neue Datei.  
  
 Finden Sie unter [Technische Hinweis 22](../../mfc/tn022-standard-commands-implementation.md) Informationen zum Standardverhalten und Hinweise für diese Member-Funktion außer Kraft setzen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileopen"></a>CWinApp::OnFileOpen  
 Implementiert die `ID_FILE_OPEN` Befehl.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn aktiviert, behandelt diese Funktion Ausführung des Befehls Datei öffnen.  
  
 Informationen zum Standardverhalten und Hinweise für diese Member-Funktion außer Kraft setzen, finden Sie unter [Technische Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Implementiert die **ID_FILE_PRINT_SETUP** Befehl.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Ist diese Einstellung aktiviert ist, behandelt diese Funktion die Ausführung des Befehls Drucken der Datei.  
  
 Informationen zum Standardverhalten und Hinweise für diese Member-Funktion außer Kraft setzen, finden Sie unter [Technische Hinweis 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing Nr.&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onhelp"></a>CWinApp::OnHelp  
 Verarbeitet die F1-Hilfe in der Anwendung (unter Verwendung des aktuellen Kontexts).  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel fügen Sie auch einen Zugriffstaste Eintrag für die F1-Taste. Aktivieren die F1-Taste ist nur eine Konvention, nicht erforderlich.  
  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_HELP, OnHelp )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn aktiviert, vom Framework aufgerufen, wenn der Benutzer die F1-Taste drückt.  
  
 Die standardmäßige Implementierung dieser Funktion Meldungshandler bestimmt den Hilfekontext, der das aktuelle Fenster, Dialogfeld oder Menüelement entspricht, und ruft dann WINHELP. EXE-DATEI. Wenn kein Kontext verfügbar ist, verwendet die Funktion den Standardkontext.  
  
 Überschreiben Sie diese Memberfunktion zum Festlegen, des Hilfekontext als das Fenster, das Dialogfeld, Menüelement oder Symbolleisten-Schaltfläche, die gegenwärtig den Fokus besitzt. Rufen Sie `WinHelp` können Sie mit den gewünschten Kontext-ID  
  
##  <a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 Behandelt das **ID_HELP_FINDER** und **ID_DEFAULT_HELP** Befehle.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn aktiviert, ruft das Framework diese Meldungshandler Funktion, wenn der Benutzer der Anwendung aufzurufenden Befehls Hilfe Finder auswählt `WinHelp` mit dem Standard **HELP_FINDER** Thema.  
  
##  <a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 Behandelt das **ID_HELP_INDEX** Befehl und ein Standardthema enthält.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn aktiviert, ruft das Framework diese Meldungshandler Funktion, wenn der Benutzer der Anwendung aufzurufenden Befehls den Index auswählt `WinHelp` mit dem Standard **HELP_INDEX** Thema.  
  
##  <a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 Behandelt das **ID_HELP_USING** Befehl.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie hinzufügen, ein `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` -Anweisung die `CWinApp` Klasse meldungszuordnung diese Member-Funktion zu aktivieren. Wenn der Benutzer der Anwendung aufzurufenden Befehls erhöhen mithilfe auswählt, ruft das Framework diese Meldungshandlerfunktion der `WinHelp` Anwendung mit dem Standard **HELP_HELPONHELP** Thema.  
  
##  <a name="onidle"></a>OnIdle  
 Überschreiben Sie diese Member-Funktion, um die Zeit im Leerlauf Verarbeitung durchzuführen.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Ein Zähler jedes Mal erhöht `OnIdle` wird aufgerufen, wenn die Anwendung Warteschlange leer ist. Dieser Zähler wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die `lCount` Parameter, um die relative Dauer zu ermitteln, die Anwendung im Leerlauf ohne eine Nachricht verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL erhalten mehr Leerlaufzeiten; 0, wenn keine weiteren Leerlaufzeit erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 `OnIdle`wird in der Standardeinstellung Nachrichtenschleife aufgerufen werden, wenn die Anwendung Warteschlange leer ist. Verwenden Sie überschreiben, um einen eigenen Hintergrund Aufgaben im Leerlauf-Handler aufzurufen.  
  
 `OnIdle`sollte zurückgeben 0 an, um anzugeben, dass keine Leerlaufzeiten erforderlich ist. Die `lCount` Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist und wird jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können die anderen im Leerlauf Routinen, die basierend auf diese Anzahl aufrufen.  
  
 Es folgt eine Zusammenfassung Leerlaufschleifen-Verarbeitung aus:  
  
1.  Wenn die Schleife in der Microsoft Foundation Class-Bibliothek die Nachrichtenwarteschlange überprüft und keine ausstehenden Nachrichten findet, ruft es `OnIdle` für die Application-Objekt und gibt 0, als die `lCount` Argument.  
  
2. `OnIdle`führt einige Verarbeitung und gibt ein Wert ungleich NULL an, dass er sollte wieder aufgerufen werden, hierzu weitere Verarbeitung.  
  
3.  Die Nachrichtenschleife prüft die Warteschlange erneut aus. Wenn keine Nachrichten ausstehen, ruft es `OnIdle` in diesem Fall erhöht der `lCount` Argument.  
  
4.  Schließlich `OnIdle` seine Leerlaufaufgaben Verarbeitung beendet und gibt 0 zurück. Daraufhin wird die Schleife beendet Aufrufen `OnIdle` bis die nächste Nachricht aus der Warteschlange empfangen wird, an welcher Stelle im Leerlauf Zyklus neu gestartet wird mit dem Argument auf 0 festgelegt.  
  
 Führen Sie keine langwierige Aufgaben während der `OnIdle` da Ihre Anwendung auf Benutzereingaben bis verarbeiten kann `OnIdle` zurückgibt.  
  
> [!NOTE]
>  Die standardmäßige Implementierung des `OnIdle` Updates Befehl Benutzeroberflächenobjekte, z. B. Menüelemente und Symbolleisten-Schaltflächen und interne Daten Struktur Cleanup ausgeführt werden. Daher überschreiben `OnIdle`, müssen Sie aufrufen, `CWinApp::OnIdle` mit der `lCount` in der überschriebenen Version. Rufen Sie zuerst alle Basisklassen leerlaufverarbeitung (d. h. bis die Basisklasse `OnIdle` gibt 0 zurück). Wenn Sie müssen ausgeführt werden, bevor der Basisklassen-Verarbeitung abgeschlossen ist, überprüfen Sie die Implementierung der Basisklasse zum Auswählen des richtigen `lCount` , um Ihre Arbeit benötigen.  
  
 Wenn Sie nicht möchten `OnIdle` um aufgerufen, wenn eine Nachricht aus der Warteschlange abgerufen wird, können Sie überschreiben die [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Wenn eine Anwendung einen sehr kurzen Zeitgeber festgelegt wurde, oder wenn vom System gesendet wird die **WM_SYSTIMER** Nachricht dann `OnIdle` wird wiederholt aufgerufen, und die Leistung beeinträchtigen.  
  
### <a name="example"></a>Beispiel  
 Die folgenden beiden Beispiele zeigen, wie mit `OnIdle`. Im erste Beispiel verarbeitet zwei Leerlaufaufgaben mithilfe der `lCount` Argument für die Aufgaben zu priorisieren. Die erste Aufgabe ist hohe Priorität sollten, und Sie sie wann immer möglich. Der zweite Task ist weniger wichtig und sollten nur, wenn eine lange Pause Benutzereingaben ausgeführt werden. Beachten Sie, dass die Basisklassenversion von `OnIdle`. Im zweite Beispiel wird eine Gruppe von Leerlaufaufgaben mit unterschiedlichen Prioritäten verwaltet.  
  
 [!code-cpp[NVC_MFCWindowing&51;](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>CWinApp:: OpenDocumentFile  
 Das Framework ruft diese Methode zum Öffnen der benannten [CDocument](../../mfc/reference/cdocument-class.md) Datei für die Anwendung.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszFileName`  
 Der Name der Datei, die geöffnet werden.  
  
 [in] `bAddToMRU`  
 `TRUE`Gibt an, dass das Dokument ist eine der neuesten Dateien. `FALSE` gibt an, das Dokument ist nicht die aktuellsten Dateien.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDocument` Wenn erfolgreich, andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Dokument mit diesem Namen bereits geöffnet ist, wird das erste Frame-Fenster, das das Dokument enthält den Fokus erhalten. Wenn eine Anwendung mehrere Dokumentvorlagen unterstützt, verwendet das Framework die Erweiterung finden Sie die entsprechenden Dokumentvorlage, die versuchen, das Dokument zu laden. Wenn erfolgreich ist, erstellt die Dokumentvorlage ein Rahmenfenster und Ansicht für das Dokument.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 Rufen Sie diese Memberfunktion zum Analysieren von der Befehlszeile und die Parameter, jeweils einen Dienst zu senden [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `rCmdInfo`  
 Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Starten eines neuen MFC-Projekts mit dem Assistenten erstellt der Assistent eine lokale Instanz von `CCommandLineInfo`, und rufen Sie dann `ProcessShellCommand` und `ParseCommandLine` in der [InitInstance](#initinstance) Member-Funktion. Eine Befehlszeile folgt die unten beschriebene Route:  
  
1.  Nach dem Erstellen `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.  
  
2. `ParseCommandLine`Ruft dann `CCommandLineInfo::ParseParam` wiederholt, einmal für jeden Parameter.  
  
3. `ParseParam`füllt die `CCommandLineInfo` -Objekt, das dann an [ProcessShellCommand ein](#processshellcommand).  
  
4. `ProcessShellCommand`behandelt die Befehlszeilenargumente und Flags.  
  
 Beachten Sie, die Sie aufrufen können `ParseCommandLine` direkt nach Bedarf.  
  
 Eine Beschreibung der Flags, die Befehlszeile finden Sie unter [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).  
  
##  <a name="pretranslatemessage"></a>PreTranslateMessage  
 Überschreiben Sie diese Funktion Fenster, Nachrichten zu filtern, bevor sie an die Windows-Funktionen verteilt sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) die standardmäßige Implementierung führt Zugriffstaste Übersetzung aus, damit Sie aufrufen, müssen die `CWinApp::PreTranslateMessage` Member-Funktion in der überschriebenen Version.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Ein Zeiger auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Meldung in vollständig verarbeitet wurde `PreTranslateMessage` und nicht weiter verarbeitet werden soll. 0 (null), wenn die Nachricht auf die übliche Weise verarbeitet werden soll.  
  
##  <a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
 Hookfunktion für das Framework ruft diese Memberfunktion zum Filtern und bestimmte Windows-Meldungen zu reagieren.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 Gibt einen Hookcode. Diese Memberfunktion verwendet der Code zum Bestimmen der Verarbeitung`lpMsg.`  
  
 `lpMsg`  
 Ein Zeiger auf ein Windows [MSG](../../mfc/reference/msg-structure1.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Hookfunktion verarbeitet Ereignisse, bevor sie die Anwendung normal-Nachricht gesendet werden verarbeitet.  
  
 Wenn Sie diese erweiterte Funktion überschreiben, müssen Sie die Basisklassenversion zum Verwalten des Frameworks aufrufen Verarbeitung zu verknüpfen.  
  
##  <a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 Von dieser Memberfunktion aufgerufen [InitInstance](#initinstance) aus übergebenen Parameter akzeptiert die `CCommandLineInfo` identifizierte Objekt `rCmdInfo`, und die angegebene Aktion auszuführen.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `rCmdInfo`  
 Ein Verweis auf eine [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Shellbefehl erfolgreich verarbeitet wird. Bei 0 zurückgeben **FALSE** von [InitInstance](#initinstance).  
  
### <a name="remarks"></a>Hinweise  
 Beim Starten eines neuen MFC-Projekts mit dem Assistenten erstellt der Assistent eine lokale Instanz von `CCommandLineInfo`, und rufen Sie dann `ProcessShellCommand` und [ParseCommandLine](#parsecommandline) in der `InitInstance` Member-Funktion. Eine Befehlszeile folgt die unten beschriebene Route:  
  
1.  Nach dem Erstellen `InitInstance`, `CCommandLineInfo` -Objekt übergeben wird `ParseCommandLine`.  
  
2. `ParseCommandLine`Ruft dann [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) wiederholt, einmal für jeden Parameter.  
  
3. `ParseParam`füllt die `CCommandLineInfo` -Objekt, das dann an `ProcessShellCommand`.  
  
4. `ProcessShellCommand`behandelt die Befehlszeilenargumente und Flags.  
  
 Der Datenmember der `CCommandLineInfo` identifizierte Objekt [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), sind von den folgenden Aufzählungstyp, die in definiert ist die `CCommandLineInfo` Klasse.  
  
 `enum {`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `};`  
  
 Eine kurze Beschreibung jeder dieser Werte finden Sie unter `CCommandLineInfo::m_nShellCommand`.  
  
##  <a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 Das Framework ruft diese Memberfunktion auf, wenn der Handler eine Nachricht von der Anwendung oder Befehlshandler ausgelöste Ausnahme nicht abfängt.  
  
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
 Der Wert, der an Windows zurückgegeben werden soll. Normalerweise ist dies 0L für Windows-Meldungen 1L ( **TRUE**) für Command-Meldungen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nicht direkt.  
  
 Die standardmäßige Implementierung von dieser Memberfunktion wird ein Meldungsfeld erstellt. Im Meldungsfeld angezeigt, wenn die nicht abgefangene Ausnahme durch ein Menü, eine Symbolleiste oder ein Accelerator-Befehl fehlgeschlagen stammt, eine Meldung "Fehler beim Befehl"; Andernfalls wird eine Meldung "Interner Anwendungsfehler".  
  
 Überschreiben Sie diese Memberfunktion zum globalen Behandlung für die Ausnahmen bereitzustellen. Rufen Sie nur die Basisfunktionalität, wenn Sie im Meldungsfeld angezeigt werden soll.  
  
##  <a name="register"></a>CWinApp::Register  
 Führt alle Registrierungsaufgaben aus nicht von verarbeitet `RegisterShellFileTypes`.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt einfach "true" zurück. Überschreiben Sie diese Funktion, um alle benutzerdefinierten Registrierungsschritten bereitzustellen.  
  
##  <a name="registershellfiletypes"></a>CWinApp:: RegisterShellFileTypes  
 Rufen Sie diese Memberfunktion, um alle Dokumenttypen Ihrer Anwendung mit dem Windows-Datei-Manager registriert.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCompat`  
 `TRUE`Fügt die Registrierungseinträge für Shell-Befehle Druck- und drucken, sodass Benutzer Dateien direkt von der Shell oder ziehen die Datei auf einem Printer-Objekt zu drucken. Außerdem wird einen DefaultIcon Schlüssel hinzugefügt. Dieser Parameter ist standardmäßig `FALSE` um Abwärtskompatibilität zu gewährleisten.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht es dem Benutzer zum Öffnen einer Datendatei, die von der Anwendung durch Doppelklicken sie im Datei-Manager erstellt. Rufen Sie `RegisterShellFileTypes` nach dem Aufruf von [AddDocTemplate](#adddoctemplate) für jede der Dokumentvorlagen in Ihrer Anwendung. Aufrufen der [EnableShellOpen](#enableshellopen) Member-Funktion, die beim Aufruf von `RegisterShellFileTypes`.  
  
 `RegisterShellFileTypes`durchläuft die Liste der [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekten, die von die Anwendung verwaltet, und fügt für jede Dokumentvorlage Einträge in die Registrierungsdatenbank, die Windows für dateizuordnungen verwaltet. Datei-Manager verwendet diese Einträge, um eine Datei zu öffnen, wenn der Benutzer darauf doppelklickt. Hierdurch entfällt die Notwendigkeit für den Versand ein. REG-Datei mit der Anwendung.  
  
> [!NOTE]
> `RegisterShellFileTypes`funktioniert nur, wenn der Benutzer das Programm mit Administratorrechten ausgeführt wird. Wenn die Anwendung nicht über Administratorrechte verfügt, können sie Registrierungsschlüssel nicht ändern.  
  
 Wenn die Registrierungsdatenbank bereits eine Erweiterung des angegebenen Dateinamen mit einem anderen Dateiformat zuordnet, wird keine neue Zuordnung erstellt. Finden Sie unter der `CDocTemplate` Klasse für das Format der Zeichenfolgen erforderlich, dass diese Informationen.  
  
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
|[in] `bRegisterRecoveryCallback`|`TRUE`Gibt an, dass diese Instanz der Anwendung eine Rückruffunktion Wiederherstellung verwendet. `FALSE` gibt an, dass dies nicht der Fall. Das Framework Ruft die Recovery-Callback-Funktion, wenn die Anwendung unerwartet beendet wird. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `strRestartIdentifier`|Die eindeutige Zeichenfolge, die diese Instanz des Neustart-Managers identifiziert. Der Neustart-Manager-Bezeichner ist eindeutig für jede Instanz einer Anwendung.|  
|[in] `pwzCommandLineArgs`|Eine Zeichenfolge, die zusätzliche Argumente über die Befehlszeile enthält.|  
|[in] `dwRestartFlags`|Optionale Kennzeichen für den Neustart-Manager. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|[in] `pRecoveryCallback`|Die Rückruffunktion für die Wiederherstellung. Diese Funktion muss annehmen einer `LPVOID` Parameter als Eingabe und der Rückgabewert ein `DWORD`. Die Standardrückruffunktion für die Wiederherstellung ist `CWinApp::ApplicationRecoveryCallback`.|  
|[in] `lpvParam`|Der Eingabeparameter für die Wiederherstellung Callback-Funktion. Weitere Informationen finden Sie unter [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `dwPingInterval`|Die Länge der Zeit, die der Neustart-Manager wartet, bis die Wiederherstellung Callback-Funktion zurückgeben. Dieser Parameter wird in Millisekunden angegeben.|  
|[in] `dwCallbackFlags`|Flags, die an die Recovery-Callback-Funktion übergeben werden. Für zukünftige Verwendung reserviert.|  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung die Standard-MFC-Implementierung für die automatische Speicherung von Dateien verwendet, verwenden Sie die einfache Version eines `RegisterWithRestartManager`. Die komplexe Version von `RegisterWithRestartManager` , wenn Sie die automatische Speicherung Verhalten der Anwendung anpassen möchten.  
  
 Wenn Sie diese Methode mit einer leeren Zeichenfolge aufrufen `strRestartIdentifier`, `RegisterWithRestartManager` erstellt eine eindeutige Zeichenfolge für diese Instanz an den Neustart-Manager.  
  
 Wenn eine Anwendung unerwartet beendet wird, wird der Neustart-Manager startet die Anwendung von der Befehlszeile aus neu und stellt den eindeutigen Bezeichner als optionales Argument, neu gestartet. In diesem Fall ruft das Framework `RegisterWithRestartManager` zweimal. Der erste Aufruf stammt [CWinApp:: InitInstance](#initinstance) mit einer leeren Zeichenfolge für den Zeichenfolgenbezeichner. Klicken Sie dann die Methode [CWinApp::ProcessShellCommand](#processshellcommand) Aufrufe `RegisterWithRestartManager` mit dem Neustart des eindeutigen Bezeichner.  
  
 Nachdem Sie eine Anwendung mit den Neustart-Manager registrieren, wird die Anwendung von der Neustart-Manager überwacht. Wenn die Anwendung unerwartet beendet wird, ruft der Neustart-Manager die Wiederherstellung Callback-Funktion bei der beendet wird. Der Neustart-Manager wartet der `dwPingInterval` auf eine Antwort von der Wiederherstellung Callback-Funktion. Wenn die Rückruffunktion Wiederherstellung innerhalb dieses Zeitraums nicht reagiert, beendet die Anwendung ohne Ausführung der Rückruffunktion Wiederherstellung.  
  
 In der Standardeinstellung die DwRestartFlags werden nicht unterstützt, jedoch werden für die zukünftige Verwendung bereitgestellt. Die möglichen Werte für `dwRestartFlags` lauten wie folgt:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 Bestimmt, ob der Neustart-Manager die Dateien, die geöffnet waren öffnet, wenn die Anwendung unerwartet beendet.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt den Neustart-Manager wieder zuvor geöffneten Dateien an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="restartinstance"></a>CWinApp::RestartInstance  
 Verarbeitet einen Neustart der Anwendung durch den Neustart-Manager initiiert.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Data Recovery Ereignishandler öffnet zuvor öffnen Sie Dokumente; `FALSE` Wenn Daten Recovery-Handler einen Fehler aufweist oder wenn keine vorher geöffnete Dokumente sind.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Neustart-Manager eine Anwendung neu gestartet wird, ruft das Framework diese Methode. Diese Methode ruft den Recovery-Datenhandler ab und stellt die automatisch gespeicherte Dateien wieder her. Diese Methode ruft [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) zu bestimmen, ob der Benutzer die automatisch gespeicherte Dateien wiederherstellen möchte.  
  
 Diese Methode gibt `FALSE` Wenn das [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) feststellt, dass keine Dokumente geöffnet sind. Wenn keine geöffneten Dokumente wurden, startet die Anwendung in der Regel.  
  
##  <a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 Bestimmt, ob der Neustart-Manager automatisch gespeicherte Dateien wiederherstellt, wenn sie die Anwendung neu gestartet wird.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt die Neustart-Manager stellt automatisch gespeicherte Dateien an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="run"></a>CWinApp:: Run  
 Stellt eine Standard-Nachrichtenschleife.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` -Wert, der von zurückgegebene `WinMain`.  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** reserviert und Windows-Meldungen sendet, bis die Anwendung empfängt eine **WM_QUIT** Nachricht. Wenn die Anwendung Nachrichtenwarteschlange derzeit keine Nachrichten enthält **ausführen** Aufrufe [OnIdle](#onidle) leerlaufzeitverarbeitung ausführen. Eingehende Nachrichten werden an die [PreTranslateMessage](#pretranslatemessage) Memberfunktion zur speziellen Verarbeitung und dann in der Windows-Funktion **TranslateMessage** für die Standardtastatur Übersetzung; schließlich die **DispatchMessage** Windows-Funktion wird aufgerufen.  
  
 **Führen Sie** wird selten überschrieben werden, Sie können jedoch überschreiben, um die besonderen Funktionen.  
  
##  <a name="runautomated"></a>CWinApp::RunAutomated  
 Rufen Sie diese Funktion, um zu bestimmen, ob die " **/Automation**"oder" **-Automatisierung**" Option vorhanden ist, der angibt, ob die Serveranwendung von einer Clientanwendung gestartet wurde.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Option gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls vorhanden, wird die Option in der Befehlszeile entfernt. Weitere Informationen über OLE-Automatisierung finden Sie im Artikel [Automatisierungsserver](../../mfc/automation-servers.md).  
  
##  <a name="runembedded"></a>CWinApp::RunEmbedded  
 Rufen Sie diese Funktion, um zu bestimmen, ob die " **/einbetten**"oder" **-Embedding**" Option vorhanden ist, der angibt, ob die Serveranwendung von einer Clientanwendung gestartet wurde.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Option gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls vorhanden, wird die Option in der Befehlszeile entfernt. Weitere Informationen zum Einbetten finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
##  <a name="saveallmodified"></a>CWinApp::SaveAllModified  
 Aufgerufen, zum Speichern aller Dokumente bei Hauptrahmenfenster für die Anwendung geschlossen werden oder durch eine `WM_QUERYENDSESSION` Nachricht.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn sicher ist, die Anwendung beenden; 0, wenn Sie nicht sicher sind, um die Anwendung zu beenden.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung von dieser Memberfunktion der [SaveModified](../../mfc/reference/cdocument-class.md#savemodified) Memberfunktion wiederum für alle geänderten Dokumente innerhalb der Anwendung.  
  
##  <a name="selectprinter"></a>CWinApp::SelectPrinter  
 Rufen Sie diese Memberfunktion, um einen bestimmten Drucker auszuwählen, und lassen Sie den Drucker, der zuvor im Dialogfeld Drucken ausgewählt wurde.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hDevNames`  
 Ein Handle für ein [DEVNAMES](../../mfc/reference/devnames-structure.md) -Struktur, die den Treiber, Gerät und Port Ausgabenamen eines bestimmten Druckers identifiziert.  
  
 `hDevMode`  
 Ein Handle für ein [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) -Struktur, die Informationen über die Initialisierung für Grafikgeräte und die Umgebung eines Druckers angibt.  
  
 *bFreeOld*  
 Gibt den zuvor ausgewählten Drucker frei.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beide `hDevMode` und `hDevNames` sind **NULL**, `SelectPrinter` den Standarddrucker verwendet.  
  
##  <a name="sethelpmode"></a>CWinApp::SetHelpMode  
 Stellt die Anwendung Help ein.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>Parameter  
 `eHelpType`  
 Gibt den Typ der Hilfe verwenden. Finden Sie unter [CWinApp::m_eHelpType](#m_ehelptype) Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Stellt die Anwendung Help ein.  
  
 Sie können zum Festlegen der Anwendungstyp Hilfe auf HTMLHelp Aufrufen [EnableHTMLHelp](#enablehtmlhelp). Wenn Sie aufrufen `EnableHTMLHelp`, muss die Anwendung HTMLHelp als seine Hilfe-Anwendung verwenden. Wenn Sie ändern, um die WinHelp verwenden möchten, können Sie aufrufen `SetHelpMode` und `eHelpType` auf **AfxWinHelp**.  
  
##  <a name="setregistrykey"></a>CWinApp::SetRegistryKey  
 Bewirkt, dass Einstellungen in der Registrierung anstelle von INI-Dateien gespeichert werden.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszRegistryKey*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Schlüssels enthält.  
  
 *nIDRegistryKey*  
 Die ID einer Zeichenfolgenressource mit dem Namen des Registrierungsschlüssels.  
  
### <a name="remarks"></a>Hinweise  
 Setzt diese Funktion *M_pszRegistryKey*, die anschließend vom verwendet die `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, und `WriteProfileString` Memberfunktionen der `CWinApp`. Wenn diese Funktion aufgerufen wurde, wird die Liste der zuletzt verwendeten (MRU)-Dateien auch in der Registrierung gespeichert. Der Registrierungsschlüssel ist normalerweise der Name eines Unternehmens. Befindet sich in einem Schlüssel im folgenden Format: HKEY_CURRENT_USER\Software\\<company></company>\>\\<application></application>\>\\<section></section>\>\\<value></value>\>.  
  
##  <a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 Bestimmt, ob der Neustart-Manager eine Anwendung wiederhergestellt, die unerwartet beendet.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt den Neustart-Manager stellt die Anwendung an. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 Bestimmt, ob der Neustart-Manager speichert Dokumente in regelmäßigen Abständen zu öffnen.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager speichert Dokumente zu öffnen. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 Bestimmt, ob der Neustart-Manager automatisch alle Dokumente öffnen, wenn die Anwendung neu gestartet wird.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager speichert Dokumente öffnen, wenn die Anwendung neu gestartet wird. `FALSE` gibt an, der Neustart-Manager nicht.  
  
##  <a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 Bestimmt, ob die Anwendung vom Neustart-Manager unterstützt.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass die Anwendung den Neustart-Manager unterstützt. `FALSE` gibt an, die Anwendung nicht.  
  
##  <a name="unregister"></a>CWinApp::Unregister  
 Hebt die Registrierung aller Dateien, die von dem Application-Objekt registriert.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die `Unregister` Funktion macht die Registrierung vom Anwendungsobjekt ausgeführt und die [registrieren](#register) Funktion. Beide Funktionen wird normalerweise durch MFC werden implizit aufgerufen, und daher nicht in Ihrem Code angezeigt.  
  
 Überschreiben Sie diese Funktion zum Aufheben der Registrierung des benutzerdefinierten Schritte ausführen.  
  
##  <a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 Rufen Sie diese Memberfunktion zum Aufheben der Registrierung alle Dokumenttypen für Ihre Anwendung mit dem Windows-Datei-Manager.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="winhelp"></a>CWinApp::WinHelp  
 Rufen Sie diese Memberfunktion zum WinHelp-Anwendung aufzurufen.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 `dwData`  
 Gibt zusätzliche Daten an. Der verwendete Wert hängt vom Wert von der `nCmd` Parameter.  
  
 `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und Einfluss auf die `dwData` -Parameter finden Sie unter der [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) -Funktion von Windows.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft auch diese Funktion, um die WinHelp-Anwendung aufzurufen.  
  
 Das Framework wird die WinHelp-Anwendung automatisch geschlossen, wenn die Anwendung beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#53;](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="writeprofilebinary"></a>CWinApp:: WriteProfileBinary  
 Rufen Sie diese Memberfunktion zum Schreiben von Binärdaten in den angegebenen Abschnitt der Registrierung der Anwendung oder. INI-Datei.  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination aus Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag im angegebenen Abschnitt nicht vorhanden ist, wird es erstellt.  
  
 `pData`  
 Verweist auf die Daten geschrieben werden.  
  
 `nBytes`  
 Enthält die Anzahl der zu schreibenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` zum Abrufen der CWinApp-Klasse, die zur Veranschaulichung einer Möglichkeit, `WriteProfileBinary` und `GetProfileBinary` aus jeder Funktion in einer MFC-Anwendung verwendet werden können.  
  
 [!code-cpp[NVC_MFCWindowing&#54;](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileBinary](#getprofilebinary).  
  
##  <a name="writeprofileint"></a>CWinApp:: Writeprofileint  
 Rufen Sie diese Memberfunktion um den angegebenen Wert in den angegebenen Abschnitt der Registrierung der Anwendung zu schreiben oder. INI-Datei.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination aus Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag im angegebenen Abschnitt nicht vorhanden ist, wird es erstellt.  
  
 `nValue`  
 Enthält den Wert geschrieben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `CWinApp* pApp = AfxGetApp();` zum Abrufen der CWinApp-Klasse, die zur Veranschaulichung einer Möglichkeit, `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, und `GetProfileInt` kann von keiner Funktion in einer MFC-Anwendung verwendet werden.  
  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 Rufen Sie diese Memberfunktion, um die angegebene Zeichenfolge in den angegebenen Abschnitt der Registrierung der Anwendung zu schreiben oder. INI-Datei.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSection`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Abschnitt mit dem Eintrag angibt. Wenn der Abschnitt nicht vorhanden ist, wird es erstellt. Der Name des Abschnitts ist Kleinschreibung unterschieden. die Zeichenfolge kann eine beliebige Kombination aus Groß- und Kleinbuchstaben sein.  
  
 `lpszEntry`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Eintrag enthält, in dem der Wert geschrieben werden. Wenn der Eintrag im angegebenen Abschnitt nicht vorhanden ist, wird es erstellt. Wenn dieser Parameter `NULL`, vom angegebenen Abschnitt `lpszSection` wird gelöscht.  
  
 `lpszValue`  
 Verweist auf die Zeichenfolge geschrieben werden. Wenn dieser Parameter `NULL`, den angegebenen Eintrag der `lpszEntry` Parameter gelöscht wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Ein weiteres Beispiel finden Sie im Beispiel für [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="setappid"></a>CWinApp::SetAppID  
 Explizit festlegt Modell Benutzer-ID für die Anwendung. Diese Methode sollte aufgerufen werden, bevor eine Benutzeroberfläche für den Benutzer angezeigt wird (am besten ist der Anwendungskonstruktor).  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcszAppID`  
 Gibt die Anwendung Benutzer-Modell-ID.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [CWinThread-Klasse](../../mfc/reference/cwinthread-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Gewusst wie: Hinzufügen von Unterstützung für Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)




