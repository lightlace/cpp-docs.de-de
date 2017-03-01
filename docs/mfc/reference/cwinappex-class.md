---
title: CWinAppEx Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinAppEx
dev_langs:
- C++
helpviewer_keywords:
- CWinAppEx class
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
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
ms.openlocfilehash: 6931f1e794116882722e402c9cb95acec1ebdfd5
ms.lasthandoff: 02/24/2017

---
# <a name="cwinappex-class"></a>CWinAppEx-Klasse
`CWinAppEx`behandelt den Anwendungszustand, speichert den Zustand in der Registrierung, lädt den Zustand aus der Registrierung, initialisiert Anwendungsmanager und stellt Links zu diesen anwendungsmanagern bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](#cwinappex)|Erstellt ein `CWinAppEx`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinAppEx::CleanState](#cleanstate)|Entfernt Informationen über die Anwendung aus der Windows-Registrierung.|  
|[CWinAppEx::EnableLoadWindowPlacement](#enableloadwindowplacement)|Gibt an, ob die Anwendung die ursprüngliche Größe und Position des Hauptrahmenfenster aus der Registrierung geladen werden.|  
|[CWinAppEx::EnableTearOffMenus](#enabletearoffmenus)|Ermöglicht abtrennbare Menüs für die Anwendung.|  
|[CWinAppEx::EnableUserTools](#enableusertools)|Ermöglicht den Benutzer, benutzerdefinierte Menübefehle in der Anwendung zu erstellen.|  
|[CWinAppEx::ExitInstance](#exitinstance)|Vom Framework aufgerufen wird, innerhalb der `Run` Member-Funktion, um diese Instanz der Anwendung zu beenden. (Überschreibt [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).)|  
|[CWinAppEx::GetBinary](#getbinary)|Liest die binäre Daten, die den angegebenen Registrierungswert zugeordnet ist.|  
|[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)|Gibt einen Zeiger auf die globale [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.|  
|[CWinAppEx::GetDataVersion](#getdataversion)||  
|[CWinAppEx::GetDataVersionMajor](#getdataversionmajor)|Gibt die Hauptversion der Anwendung in der Windows-Registrierung gespeichert.|  
|[CWinAppEx::GetDataVersionMinor](#getdataversionminor)|Gibt die Nebenversion der Anwendung in der Windows-Registrierung gespeichert.|  
|[CWinAppEx::GetInt](#getint)|Liest die numerische Daten, die den angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)|Gibt einen Zeiger auf die globale [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) Objekt.|  
|[CWinAppEx::GetMouseManager](#getmousemanager)|Gibt einen Zeiger auf die globale [CMouseManager](../../mfc/reference/cmousemanager-class.md) Objekt.|  
|[CWinAppEx::GetObject](#getobject)|Liest `CObject`-abgeleitete Daten, die den angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetRegSectionPath](#getregsectionpath)|Gibt eine Zeichenfolge, die den Pfad eines Registrierungsschlüssels. Dieser Pfad verkettet die angegebenen relativen Pfad mit dem Anwendungspfad.|  
|[CWinAppEx::GetRegistryBase](#getregistrybase)|Gibt den Registrierungspfad für die Anwendung zurück.|  
|[CWinAppEx::GetSectionBinary](#getsectionbinary)|Liest die binäre Daten, die dem angegebenen Schlüssel und Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetSectionInt](#getsectionint)|Liest numerische Daten aus der Registrierung mit dem angegebenen Schlüssel und Wert.|  
|[CWinAppEx::GetSectionObject](#getsectionobject)|Liest `CObject` Daten, die dem angegebenen Schlüssel und Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetSectionString](#getsectionstring)|Liest die Zeichenfolgendaten, die dem angegebenen Schlüssel und Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetShellManager](#getshellmanager)|Gibt einen Zeiger auf die globale [CShellManager](../../mfc/reference/cshellmanager-class.md) Objekt.|  
|[CWinAppEx::GetString](#getstring)|Liest die Daten für die Zeichenfolge, die den angegebenen Wert aus der Registrierung zugeordnet ist.|  
|[CWinAppEx::GetTooltipManager](#gettooltipmanager)|Gibt einen Zeiger auf die globale [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) Objekt.|  
|[CWinAppEx::GetUserToolsManager](#getusertoolsmanager)|Gibt einen Zeiger auf die globale [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) Objekt.|  
|[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)|Initialisiert das `CContextMenuManager` Objekt.|  
|[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)|Initialisiert das `CKeyboardManager` Objekt.|  
|[CWinAppEx::InitMouseManager](#initmousemanager)|Initialisiert das `CMouseManager` Objekt.|  
|[CWinAppEx::InitShellManager](#initshellmanager)|Initialisiert die `CShellManager` Klasse|  
|[CWinAppEx::InitTooltipManager](#inittooltipmanager)|Initialisiert die `CTooltipManager` Klasse.|  
|[CWinAppEx::IsResourceSmartUpdate](#isresourcesmartupdate)||  
|[CWinAppEx::IsStateExists](#isstateexists)|Gibt an, ob der angegebene Schlüssel in der Registrierung ist.|  
|[CWinAppEx::LoadState](#loadstate)|Lädt den Anwendungszustand aus der Registrierung.|  
|[CWinAppEx::OnAppContextHelp](#onappcontexthelp)|Vom Framework aufgerufen, wenn der Benutzer die Kontexthilfe für anfordert der **Anpassung** Dialogfeld.|  
|[CWinAppEx::OnViewDoubleClick](#onviewdoubleclick)|Ruft den benutzerdefinierten Befehl auf, wenn der Benutzer auf eine beliebige Stelle in der Anwendung doppelklickt.|  
|[CWinAppEx::OnWorkspaceIdle](#onworkspaceidle)||  
|[CWinAppEx::SaveState](#savestate)|Schreibt den Status des Anwendungsframeworks auf der Windows-Registrierung.|  
|[CWinAppEx::SetRegistryBase](#setregistrybase)|Der Pfad für den Standard-Registrierungsschlüssel festgelegt. Dieser Schlüssel dient als Stamm für alle nachfolgenden Registrierungsaufrufe.|  
|[CWinAppEx::ShowPopupMenu](#showpopupmenu)|Zeigt ein Popupmenü an.|  
|[CWinAppEx::WriteBinary](#writebinary)|Schreibt die Binärdaten in den angegebenen Registrierungswert.|  
|[CWinAppEx::WriteInt](#writeint)|Schreibt die numerischen Daten an den angegebenen Registrierungswert.|  
|[CWinAppEx::WriteObject](#writeobject)|Schreibt Daten, die von abgeleitet ist die [CObject-Klasse](../../mfc/reference/cobject-class.md) an den angegebenen Registrierungswert.|  
|[CWinAppEx::WriteSectionBinary](#writesectionbinary)|Schreibt die binäre Daten auf einen Wert, der den angegebenen Registrierungsschlüssel.|  
|[CWinAppEx::WriteSectionInt](#writesectionint)|Schreibt die numerischen Daten auf einen Wert, der den angegebenen Registrierungsschlüssel.|  
|[CWinAppEx::WriteSectionObject](#writesectionobject)|Schreibt Daten aus der `CObject` -Klasse auf einen Wert mit den angegebenen Registrierungsschlüssel.|  
|[CWinAppEx::WriteSectionString](#writesectionstring)|Schreibt die Daten der Zeichenfolge auf einen Wert, der den angegebenen Registrierungsschlüssel.|  
|[CWinAppEx::WriteString](#writestring)|Schreibt die Daten der Zeichenfolge an den angegebenen Registrierungswert.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](#loadcustomstate)|Vom Framework aufgerufen, wenn der Zustand der Anwendung geladen wurde.|  
|[CWinAppEx::LoadWindowPlacement](#loadwindowplacement)|Wird vom Framework aufgerufen, wenn die Größe und Position der Anwendung aus der Registrierung geladen. Die geladenen Daten umfasst die Größe und Position der Hauptframe, die zum Zeitpunkt der letzten der Anwendung schließen.|  
|[CWinAppEx::OnClosingMainFrame](#onclosingmainframe)|Vom Framework aufgerufen, wenn ein Hauptrahmenfenster verarbeitet `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](#preloadstate)|Vom Framework aufgerufen, unmittelbar bevor wird Zustand der Anwendung geladen.|  
|[CWinAppEx::PreSaveState](#presavestate)|Vom Framework aufgerufen, unmittelbar vor, wird der Anwendungsstatus gespeichert.|  
|[CWinAppEx::ReloadWindowPlacement](#reloadwindowplacement)|Lädt die Größe und Position des angegebenen Fensters aus der Registrierung|  
|[CWinAppEx::SaveCustomState](#savecustomstate)|Vom Framework aufgerufen, nachdem der Zustand der Anwendung in die Registrierung geschrieben.|  
|[CWinAppEx::StoreWindowPlacement](#storewindowplacement)|Aufgerufen, um die Größe und Position der Hauptframe in die Registrierung geschrieben.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinAppEx::m_bForceImageReset](#m_bforceimagereset)|Gibt an, ob das Framework alle Symbolleistenbilder werden zurückgesetzt, wenn das Rahmenfenster mit die Symbolleiste, geladen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Viele der Funktionen von MFC-Framework bereitgestellt werden, hängt die `CWinAppEx` Klasse. Integrieren der `CWinAppEx` Klasse in Ihrer Anwendung auf zwei Arten:  
  
-   Erstellen einer `CWinAppEx` -Klasse in der Haupt-Thread.  
  
-   Leiten Sie die Klasse die Hauptassembly der Anwendung von `CWinAppEx`.  
  
 Nachdem Sie integrieren `CWinAppEx` in Ihrer Anwendung können Sie eines der Anwendungsmanager initialisieren. Bevor Sie einen Anwendungsmanager verwenden, müssen Sie ihn durch Aufrufen der entsprechenden Initialisierungsmethode initialisieren. Um einen Zeiger auf einen bestimmten Manager zu erhalten, rufen Sie die zugehörige Get-Methode. Die `CWinAppEx` Klasse verwaltet die folgenden Anwendungsmanager: [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager Klasse](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager Klasse](../../mfc/reference/cusertoolsmanager-class.md), und [CMenuTearOffManager-Klasse](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinappex.h  
  
##  <a name="a-namecleanstatea--cwinappexcleanstate"></a><a name="cleanstate"></a>CWinAppEx::CleanState  
 Entfernt alle Informationen über die Anwendung aus der Windows-Registrierung.  
  
```  
virtual BOOL CleanState(LPCTSTR lpszSectionName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSectionName`  
 Eine Zeichenfolge, die einen Pfad zu einem Registrierungsschlüssel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht die Anwendungsdaten aus einem bestimmten Abschnitt der Registrierung. Sie können angeben, dass im Abschnitt zu löschen, indem Sie den Parameter `lpszSectionName`. Wenn `lpszSectionName` ist `NULL`, diese Methode verwendet standardmäßig Registrierungspfad gespeichert, dem `CWinAppEx` Objekt. Verwenden Sie zum Abrufen des Standardpfad für die Registrierung [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="a-namecwinappexa--cwinappexcwinappex"></a><a name="cwinappex"></a>CWinAppEx::CWinAppEx  
 Erstellt ein `CWinAppEx`-Objekt.  
  
```  
CWinAppEx(BOOL bResourceSmartUpdate = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bResourceSmartUpdate`  
 Ein boolescher Parameter, der angibt, ob die Workspace-Objekt sollte erkennen und Behandeln von ressourcenupdates.  
  
### <a name="remarks"></a>Hinweise  
 Die `CWinAppEx` -Klasse Initialisierungsmethoden, bietet Funktionen für das Speichern und Laden von Anwendungsinformationen in der Registrierung und globale Einstellungen steuert. Außerdem können Sie globale Manager verwenden, wie z. B. die [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md) und [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md). Jede Anwendung kann nur eine Instanz haben die `CWinAppEx` Klasse.  
  
##  <a name="a-nameenableloadwindowplacementa--cwinappexenableloadwindowplacement"></a><a name="enableloadwindowplacement"></a>CWinAppEx::EnableLoadWindowPlacement  
 Gibt an, ob die Anwendung die ursprüngliche Größe und Position des Hauptrahmenfenster aus der Registrierung geladen werden.  
  
```  
void EnableLoadWindowPlacement(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Gibt an, ob die Anwendung die ursprüngliche Größe und Position des Hauptrahmenfenster aus der Registrierung geladen.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden die Größe und Position der Hauptframe aus der Registrierung zusammen mit anderen Einstellungen der Anwendung geladen. Dies geschieht bei [CWinAppEx::LoadState](#loadstate). Wenn Sie nicht die Position des ersten Fenster aus der Registrierung laden möchten, rufen Sie diese Methode mit `bEnable` festgelegt `false`.  
  
##  <a name="a-nameenabletearoffmenusa--cwinappexenabletearoffmenus"></a><a name="enabletearoffmenus"></a>CWinAppEx::EnableTearOffMenus  
 Erstellt und initialisiert ein [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
BOOL EnableTearOffMenus(
    LPCTSTR lpszRegEntry,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszRegEntry`  
 Eine Zeichenfolge, die den Pfad eines Registrierungsschlüssels enthält. Die Anwendung verwendet diesen Registrierungsschlüssel zum Speichern von Informationen für die abtrennbare Menüs.  
  
 [in] `uiCmdFirst`  
 Die erste abtrennen aus Menü-ID.  
  
 [in] `uiCmdLast`  
 Die letzte abtrennen aus Menü-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `True`Wenn die `CMenuTearOffManager` erstellt und initialisiert; `false` , wenn ein Fehler auftritt oder wenn der `CMenuTearOffManager` bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um abtrennbare Menüs in Ihrer Anwendung zu aktivieren. Sie sollten diese Funktion aufrufen `InitInstance`.  
  
##  <a name="a-nameenableusertoolsa--cwinappexenableusertools"></a><a name="enableusertools"></a>CWinAppEx::EnableUserTools  
 Ermöglicht den Benutzer, benutzerdefinierte Menübefehle erstellen, die Tastatureingaben in der Anwendung zu reduzieren. Diese Methode erstellt eine [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) Objekt.  
  
```  
BOOL EnableUserTools(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC = RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID = 0,  
    UINT uInitDirMenuID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdToolsDummy`  
 Eine ganze Zahl ohne Vorzeichen, die das Framework als Platzhalter für die Befehls-ID des Menüs Extras Benutzer verwendet.  
  
 [in] `uiCmdFirst`  
 Die Befehls-ID für den ersten Benutzer Tool-Befehl.  
  
 [in] `uiCmdLast`  
 Die Befehls-ID für den letzten Befehl des User-Tool.  
  
 [in] `pToolRTC`  
 Eine Klasse, die die `CUserToolsManager` Objekt verwendet, um neue Benutzertools erstellen.  
  
 [in] `uArgMenuID`  
 Die Argument-Menü-ID.  
  
 [in] `uInitDirMenuID`  
 Die ID für das erste Tool-Verzeichnis.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erstellt und initialisiert ein `CUserToolsManager` Objekt. `FALSE` , wenn die Methode fehlschlägt oder wenn ein `CUserToolsManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie benutzerdefinierte Tools aktivieren, unterstützt das Framework automatisch ein dynamisches Menü, das während der Anpassung erweitert werden kann. Das Framework ordnet jedes neues Element eines externen Befehls. Das Framework ruft diese Befehle aus, bei der Auswahl des entsprechenden Elements aus der **Tools** Menü.  
  
 Jedes Mal, wenn der Benutzer ein neues Element hinzufügt, erstellt das Framework ein neues Objekt. Der Klassentyp für das neue Objekt wird durch definiert `pToolRTC`. Die `pToolRTC` Klassentyp abgeleitet werden muss die [CUserTool Klasse](../../mfc/reference/cusertool-class.md).  
  
 Weitere Informationen über Benutzertools und wie Sie diese in Ihrer Anwendung finden Sie unter [benutzerdefinierte Tools](../../mfc/user-defined-tools.md).  
  
##  <a name="a-nameexitinstancea--cwinappexexitinstance"></a><a name="exitinstance"></a>CWinAppEx::ExitInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetbinarya--cwinappexgetbinary"></a><a name="getbinary"></a>CWinAppEx::GetBinary  
 Liest binäre Daten aus einem angegebenen Registrierungsschlüssel.  
  
```  
BOOL GetBinary(
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [out] `ppData`  
 Ein Zeiger auf den Puffer, den die Methode mit der binären Daten füllt.  
  
 [out] `pBytes`  
 Ein Zeiger auf eine Ganzzahl ohne Vorzeichen, die die Methode verwendet, um die Anzahl der gelesenen Bytes zu schreiben.  
  
### <a name="return-value"></a>Rückgabewert  
 `True`Bei Erfolg; `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest die binäre Daten, die in die Registrierung geschrieben. Um Daten in der Registrierung zu schreiben, verwenden Sie die Methoden [CWinAppEx::WriteBinary](#writebinary) und [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetcontextmenumanagera--cwinappexgetcontextmenumanager"></a><a name="getcontextmenumanager"></a>CWinAppEx::GetContextMenuManager  
 Gibt einen Zeiger auf die globale [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.  
  
```  
CContextMenuManager* GetContextMenuManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CContextMenuManager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das CContextMenuManager-Objekt nicht initialisiert ist, ruft diese Funktion [CWinAppEx::InitContextMenuManager](#initcontextmenumanager) vor der Rückgabe eines Zeigers.  
  
##  <a name="a-namegetdataversiona--cwinappexgetdataversion"></a><a name="getdataversion"></a>CWinAppEx::GetDataVersion  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetDataVersion() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetdataversionmajora--cwinappexgetdataversionmajor"></a><a name="getdataversionmajor"></a>CWinAppEx::GetDataVersionMajor  
 Gibt die Hauptversion der Anwendung, die in der Windows-Registrierung gespeichert wird, beim Aufruf von [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMajor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die Hauptversionsnummer enthält.  
  
##  <a name="a-namegetdataversionminora--cwinappexgetdataversionminor"></a><a name="getdataversionminor"></a>CWinAppEx::GetDataVersionMinor  
 Gibt die Nebenversion der Anwendung, die in der Windows-Registrierung gespeichert wird, beim Aufruf von [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMinor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die Nebenversionsnummer enthält.  
  
##  <a name="a-namegetinta--cwinappexgetint"></a><a name="getint"></a>CWinAppEx::GetInt  
 Liest Daten in ganzen Zahlen aus einem angegebenen Registrierungsschlüssel.  
  
```  
int GetInt(
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen eines Registrierungseintrags enthält.  
  
 [in] `nDefault`  
 Der Standardwert, der die Methode zurückgibt, wenn der angegebene Registrierungseintrag nicht vorhanden ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Registrierungsdaten, wenn die Methode erfolgreich war; andernfalls `nDefault`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest Daten in ganzen Zahlen aus der Registrierung. Wenn keine ganzzahligen des Registrierungsschlüssels erkennbar zugeordnet Daten `lpszEntry`, gibt diese Methode `nDefault`. Um Daten in der Registrierung zu schreiben, verwenden Sie die Methoden [CWinAppEx::WriteSectionInt](#writesectionint) und [CWinAppEx::WriteInt](#writeint).  
  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetkeyboardmanagera--cwinappexgetkeyboardmanager"></a><a name="getkeyboardmanager"></a>CWinAppEx::GetKeyboardManager  
 Gibt einen Zeiger auf die globale [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) Objekt.  
  
```  
CKeyboardManager* GetKeyboardManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CKeyboardManager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Tastatur-Manager nicht initialisiert ist, ruft diese Funktion [CWinAppEx::InitKeyboardManager](#initkeyboardmanager) vor der Rückgabe eines Zeigers.  
  
##  <a name="a-namegetmousemanagera--cwinappexgetmousemanager"></a><a name="getmousemanager"></a>CWinAppEx::GetMouseManager  
 Gibt einen Zeiger auf die globale [CMouseManager](../../mfc/reference/cmousemanager-class.md) Objekt.  
  
```  
CMouseManager* GetMouseManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CMouseManager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Maus-Manager nicht initialisiert ist, ruft diese Funktion [CWinAppEx::InitMouseManager](#initmousemanager) vor der Rückgabe eines Zeigers.  
  
##  <a name="a-namegetobjecta--cwinappexgetobject"></a><a name="getobject"></a>CWinAppEx::GetObject  
 Liest [CObject](../../mfc/reference/cobject-class.md)Dervied - Daten aus der Registrierung.  
  
```  
BOOL GetObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungseintrags enthält.  
  
 [out] `obj`  
 Ein Verweis auf eine `CObject`. Die Methode verwendet diesen Verweis zum Speichern der Registrierungsdaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest Daten aus der Registrierung, die von abgeleitet ist `CObject`. Schreiben `CObject` Daten in der Registrierung verwenden Sie entweder [CWinAppEx::WriteObject](#writeobject) oder [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags, der unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetregistrybasea--cwinappexgetregistrybase"></a><a name="getregistrybase"></a>CWinAppEx::GetRegistryBase  
 Ruft den Standard-Registrierungspfad für die Anwendung ab.  
  
```  
LPCTSTR GetRegistryBase();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Pfad der Standardspeicherort für die Registrierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Alle Methoden der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) , die Zugriff auf die Registrierung Start an einem Standardspeicherort. Verwenden Sie diese Methode, um einen Pfad für den Standardspeicherort für die Registrierung abzurufen. Verwendung [CWinAppEx::SetRegistryBase](#setregistrybase) zum Ändern des Standardspeicherorts für die Registrierung.  
  
##  <a name="a-namegetregsectionpatha--cwinappexgetregsectionpath"></a><a name="getregsectionpath"></a>CWinAppEx::GetRegSectionPath  
 Erstellt und gibt den absoluten Pfad eines Registrierungsschlüssels.  
  
```  
CString GetRegSectionPath(LPCTSTR szSectionAdd = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `szSectionAdd`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , der den absoluten Pfad ein Registrierungsschlüssel enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode definiert der Registrierungsschlüssel absoluten Pfad durch Anhängen des relativen Pfads im `szSectionAdd` am Standardspeicherort für die Registrierung für Ihre Anwendung. Um den Standard-Registrierungsschlüssel zu erhalten, verwenden Sie die Methode [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="a-namegetsectionbinarya--cwinappexgetsectionbinary"></a><a name="getsectionbinary"></a>CWinAppEx::GetSectionBinary  
 Binäre Daten liest aus der Registrierung.  
  
```  
BOOL GetSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge mit dem Wert zu lesen.  
  
 [out] `ppData`  
 Ein Zeiger auf den Puffer, in dem die Methode die Daten speichert.  
  
 [out] `pBytes`  
 Ein Zeiger auf eine Ganzzahl ohne Vorzeichen. Die Methode schreibt die Größe des `ppData` für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 `True`, wenn erfolgreich, andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest die binäre Daten, die in der Registrierung mit den Methoden geschrieben werden [CWinAppEx::WriteBinary](#writebinary) und [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetsectioninta--cwinappexgetsectionint"></a><a name="getsectionint"></a>CWinAppEx::GetSectionInt  
 Integer-Daten liest aus der Registrierung.  
  
```  
int GetSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge mit dem Wert zu lesen.  
  
 [in] `nDefault`  
 Der Standardwert zurückgeben, wenn der angegebene Wert nicht vorhanden ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ganzzahligen Daten, die in den angegebenen Registrierungswert gespeichert ist; `nDefault` Wenn die Daten nicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Methoden [CWinAppEx::WriteInt](#writeint) und [CWinAppEx::WriteSectionInt](#writesectionint) ganzzahlige Daten in die Registrierung geschrieben.  
  
 Die `lpszSubSection` Parameter ist ein absoluter Pfad eines Registrierungseintrags. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetsectionobjecta--cwinappexgetsectionobject"></a><a name="getsectionobject"></a>CWinAppEx::GetSectionObject  
 Liest [CObject](../../mfc/reference/cobject-class.md) Registrierungsdaten aus der Registrierung.  
  
```  
BOOL GetSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge mit dem Wert zu lesen.  
  
 [out] `obj`  
 Ein Verweis auf eine `CObject`. Die Methode verwendet dieses `CObject` zum Speichern der Registrierungsdaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest Daten aus der Registrierung. Lesen der Daten `CObject` Daten oder für eine Klasse, die von abgeleiteten `CObject`. Schreiben `CObject` Daten in der Registrierung verwenden Sie entweder [CWinAppEx::WriteObject](#writeobject) oder [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetsectionstringa--cwinappexgetsectionstring"></a><a name="getsectionstring"></a>CWinAppEx::GetSectionString  
 Liest Daten aus der Registrierung eine Zeichenfolge.  
  
```  
CString GetSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge mit dem Wert zu lesen.  
  
 [in] `lpszDefault`  
 Der Standardwert zurückgeben, wenn der angegebene Wert nicht vorhanden ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeichenfolgendaten, die in den angegebenen Registrierungswert gespeichert, wenn die Daten vorhanden sind; andernfalls `lpszDefault`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest die Zeichenfolgendaten in die Registrierung geschrieben. Verwendung [CWinAppEx::WriteString](#writestring) und [CWinAppEx::WriteSectionString](#writesectionstring) Zeichenfolgendaten in die Registrierung geschrieben.  
  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegetshellmanagera--cwinappexgetshellmanager"></a><a name="getshellmanager"></a>CWinAppEx::GetShellManager  
 Gibt einen Zeiger auf die globale [CShellManager](../../mfc/reference/cshellmanager-class.md) Objekt.  
  
```  
CShellManager* GetShellManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CShellManager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CShellManager` Objekt ist nicht initialisiert ist, werden Aufrufe dieser Funktion [CWinAppEx::InitShellManager](#initshellmanager) vor der Rückgabe eines Zeigers.  
  
##  <a name="a-namegetstringa--cwinappexgetstring"></a><a name="getstring"></a>CWinAppEx::GetString  
 Liest eine Zeichenfolge Daten aus einem angegebenen Registrierungsschlüssel.  
  
```  
CString GetString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpzDefault= _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge mit dem Namen eines Registrierungsschlüssels  
  
 [in] `lpzDefault`  
 Der Standardwert, der die Methode zurückgibt, wenn der angegebene Registrierungseintrag nicht vorhanden ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeichenfolgendaten, die in der Registrierung im Erfolgsfall gespeichert; `lpszDefault` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode liest die Zeichenfolgendaten in die Registrierung geschrieben. Um Daten in der Registrierung zu schreiben, verwenden Sie die Methoden [CWinAppEx::WriteString](#writestring) oder [CWinAppEx::WriteSectionString](#writesectionstring).  
  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namegettooltipmanagera--cwinappexgettooltipmanager"></a><a name="gettooltipmanager"></a>CWinAppEx::GetTooltipManager  
 Gibt einen Zeiger auf die globale [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) Objekt.  
  
```  
CTooltipManager* GetTooltipManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CTooltipManager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CTooltipManager` Objekt ist nicht initialisiert ist, werden Aufrufe dieser Funktion [CWinAppEx::InitTooltipManager](#inittooltipmanager) vor der Rückgabe eines Zeigers.  
  
##  <a name="a-namegetusertoolsmanagera--cwinappexgetusertoolsmanager"></a><a name="getusertoolsmanager"></a>CWinAppEx::GetUserToolsManager  
 Gibt einen Zeiger auf die globale [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) Objekt.  
  
```  
CUserToolsManager* GetUserToolsManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die globale `CUserToolsManager` Objekt. `NULL` Wenn benutzerverwaltung-Tools für die Anwendung nicht aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Bevor Sie einen Zeiger zum Abrufen der `CUserToolsManager` -Objekt, initialisieren Sie den Manager durch Aufrufen von [CWinAppEx::EnableUserTools](#enableusertools).  
  
##  <a name="a-nameinitcontextmenumanagera--cwinappexinitcontextmenumanager"></a><a name="initcontextmenumanager"></a>CWinAppEx::InitContextMenuManager  
 Initialisiert die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.  
  
```  
BOOL InitContextMenuManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode das Objekt CContextMenuManager erstellt; 0, wenn das `CContextMenuManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [CWinAppEx::GetContextMenuManager](#getcontextmenumanager), die standardmäßige Implementierung dieser Methode ruft `InitContextMenuManager`.  
  
 Wenn die Anwendung bereits einen Kontext-Menü-Manager und Sie rufen `InitContextMenuManager`, die Anwendung muss eine [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Fehler. Aus diesem Grund sollten Sie nicht aufrufen `InitContextMenuManager` bei der Erstellung einer `CContextMenuManager` direkt. Wenn Sie nicht über eine benutzerdefinierte arbeiten `CContextMenuManager`, verwenden Sie `GetContextMenuManager` zum Erstellen einer `CContextMenuManager` Objekt.  
  
##  <a name="a-nameinitkeyboardmanagera--cwinappexinitkeyboardmanager"></a><a name="initkeyboardmanager"></a>CWinAppEx::InitKeyboardManager  
 Initialisiert die [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) Objekt.  
  
```  
BOOL InitKeyboardManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode erstellt die `CKeyboardManager` Objekt; 0, wenn das `CKeyboardManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [CWinAppEx::GetKeyboardManager](#getkeyboardmanager), die standardmäßige Implementierung dieser Methode ruft `InitKeyboardManager`.  
  
 Wenn die Anwendung bereits, einen Tastatur-Manager verfügt, und Sie rufen `InitKeyboardManager`, die Anwendung muss eine [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Fehler. Aus diesem Grund sollten Sie nicht aufrufen `InitKeyboardManager` bei der Erstellung einer `CKeyboardManager` direkt. Wenn Sie nicht über eine benutzerdefinierte arbeiten `CKeyboardManager`, verwenden Sie `GetKeyboardManager` zum Erstellen einer `CKeyboardManager` Objekt.  
  
##  <a name="a-nameinitmousemanagera--cwinappexinitmousemanager"></a><a name="initmousemanager"></a>CWinAppEx::InitMouseManager  
 Initialisiert die [CMouseManager](../../mfc/reference/cmousemanager-class.md) Objekt.  
  
```  
BOOL InitMouseManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode erstellt die `CMouseManager` Objekt; 0, wenn das `CMouseManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [CWinAppEx::GetMouseManager](#getmousemanager), die standardmäßige Implementierung dieser Methode ruft `InitMouseManager`.  
  
 Wenn die Anwendung bereits einen Maus-Manager und Sie rufen `InitMouseManager`, die Anwendung muss eine [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Fehler. Aus diesem Grund sollten Sie nicht aufrufen `InitMouseManager` bei der Erstellung einer `CMouseManager` direkt. Wenn Sie nicht über eine benutzerdefinierte arbeiten `CMouseManager`, verwenden Sie `GetMouseManager` zum Erstellen einer `CMouseManager` Objekt.  
  
##  <a name="a-nameinitshellmanagera--cwinappexinitshellmanager"></a><a name="initshellmanager"></a>CWinAppEx::InitShellManager  
 Initialisiert die [CShellManager](../../mfc/reference/cshellmanager-class.md) Objekt.  
  
```  
BOOL InitShellManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode erstellt die `CShellManager` Objekt; 0, wenn das `CShellManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [CWinAppEx::GetShellManager](#getshellmanager), die standardmäßige Implementierung dieser Methode ruft `InitShellManager`.  
  
 Wenn die Anwendung bereits einen Shell-Manager und Sie rufen `InitShellManager`, Ihre Anwendung löst eine [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Fehler. Rufen Sie daher nicht `InitShellManager` bei der Erstellung einer `CShellManager` direkt. Wenn Sie nicht über eine benutzerdefinierte arbeiten `CShellManager`, verwenden `GetShellManager` zum Erstellen einer `CShellManager` Objekt.  
  
##  <a name="a-nameinittooltipmanagera--cwinappexinittooltipmanager"></a><a name="inittooltipmanager"></a>CWinAppEx::InitTooltipManager  
 Initialisiert die [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) Objekt.  
  
```  
BOOL InitTooltipManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode erstellt die `CTooltipManager` Objekt; 0, wenn das `CTooltipManager` Objekt bereits vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [CWinAppEx::GetTooltipManager](#gettooltipmanager), die standardmäßige Implementierung dieser Methode ruft `InitTooltipManager`.  
  
 Wenn die Anwendung bereits einen QuickInfo-Manager und Sie rufen `InitTooltipManager`, die Anwendung muss eine [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) Fehler. Aus diesem Grund sollten Sie nicht aufrufen `InitTooltipManager` bei der Erstellung einer `CTooltipManager` direkt. Wenn Sie nicht über eine benutzerdefinierte arbeiten `CTooltipManager`, verwenden Sie `GetTooltipManager` zum Erstellen einer `CTooltipManager` Objekt.  
  
##  <a name="a-nameisresourcesmartupdatea--cwinappexisresourcesmartupdate"></a><a name="isresourcesmartupdate"></a>CWinAppEx::IsResourceSmartUpdate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResourceSmartUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisstateexistsa--cwinappexisstateexists"></a><a name="isstateexists"></a>CWinAppEx::IsStateExists  
 Gibt an, ob der angegebene Schlüssel in der Registrierung ist.  
  
```  
BOOL IsStateExists(LPCTSTR lpszSectionName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSectionName`  
 Eine Zeichenfolge, die einen Pfad zu einem Registrierungsschlüssel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Schlüssel in der Registrierung ist; andernfalls 0.  
  
##  <a name="a-nameloadcustomstatea--cwinappexloadcustomstate"></a><a name="loadcustomstate"></a>CWinAppEx::LoadCustomState  
 Das Framework ruft diese Methode auf, nachdem der Status der Anwendung aus der Registrierung geladen.  
  
```  
virtual void LoadCustomState();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn eine beliebige Verarbeitung erfolgen, nachdem die Anwendung den Status aus der Registrierung geladen werden soll. Standardmäßig bewirkt diese Methode nichts.  
  
 Um benutzerdefinierte Zustandsinformationen aus der Registrierung zu laden, muss die Informationen zunächst mithilfe von gespeichert werden [CWinAppEx::SaveCustomState](#savecustomstate).  
  
##  <a name="a-nameloadstatea--cwinappexloadstate"></a><a name="loadstate"></a>CWinAppEx::LoadState  
 Liest den Anwendungsstatus aus der Windows-Registrierung.  
  
```  
BOOL LoadState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
virtual BOOL LoadState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Fensterobjekt Frame. Die Methode gilt die Statusinformationen in der Registrierung für diese Rahmenfenster.  
  
 [in] `lpszSectionName`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `pFrameImpl`  
 Ein Zeiger auf ein `CFrameImpl` Objekt. Die Methode gilt die Statusinformationen in der Registrierung für diese Rahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode lädt den Zustand der Anwendung und alle Zustandsinformationen zu einem Rahmenfenster. Die geladene Informationen für das Rahmenfenster ist an der angegebenen Rahmenfenster angewendet. Wenn Sie ein Rahmenfenster nicht angeben, werden nur die anwendungsstatusinformationen geladen. Anwendungsinformationen umfasst die Statuswerte von der [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md), und die [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md).  
  
 Die standardmäßige Implementierung des `CFrameImpl::OnLoadFrame` Aufrufe `LoadState`.  
  
 Die `lpszSectionName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-nameloadwindowplacementa--cwinappexloadwindowplacement"></a><a name="loadwindowplacement"></a>CWinAppEx::LoadWindowPlacement  
 Wird vom Framework aufgerufen, wenn die Größe und Position der Hauptrahmenfenster aus der Registrierung geladen.  
  
```  
virtual BOOL LoadWindowPlacement(
    CRect& rectNormalPosition,  
    int& nFlags,  
    int& nShowCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectNormalPosition`  
 Ein Rechteck, das mit den Koordinaten der das Hauptrahmenfenster, wenn es in der wiederhergestellten Position befindet.  
  
 [out] `nFlags`  
 Flags, die die Position eines minimierten Fensters und des Betriebssystems wie zwischen einem minimierten Fenster und eine wiederhergestellte Fenster wechselt.  
  
 [out] `nShowCmd`  
 Eine ganze Zahl, die den Anzeigezustand des Fensters angibt. Weitere Informationen zu den möglichen Werten finden Sie unter [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lädt MFC automatisch die vorherige Position und den Status der Hauptrahmenfenster beim Starten der Anwendung. Weitere Informationen dazu, wie diese Informationen in der Registrierung gespeichert werden, finden Sie unter [CWinAppEx::StoreWindowPlacement](#storewindowplacement).  
  
 Überschreiben Sie diese Methode, wenn Sie weitere Informationen über das Hauptrahmenfenster laden möchten.  
  
##  <a name="a-namembforceimagereseta--cwinappexmbforceimagereset"></a><a name="m_bforceimagereset"></a>CWinAppEx::m_bForceImageReset  
 Gibt an, ob das Framework Symbolleistenbilder, die alle zurückgesetzt, wenn es das Rahmenfenster erneut geladen, das die Symbolleiste enthält.  
  
```  
BOOL m_bForceImageReset;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der `m_bForceImageReset` -Datenmember ist eine geschützte Variable.  
  
##  <a name="a-nameonappcontexthelpa--cwinappexonappcontexthelp"></a><a name="onappcontexthelp"></a>CWinAppEx::OnAppContextHelp  
 Das Framework ruft diese Methode, wenn der Benutzer die Kontexthilfe für anfordert der **Anpassung** Dialogfeld.  
  
```  
virtual void OnAppContextHelp(
    CWnd* pWndControl,  
    const DWORD dwHelpIDArray[]);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndControl`  
 Ein Zeiger auf ein Window-Objekt, das für die der Benutzer die Kontexthilfe aufgerufen.  
  
 [in] `dwHelpIDArray[]`  
 Ein reservierter Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist derzeit für die zukünftige Verwendung reserviert. Die Standardimplementierung wird keine Aktion ausgeführt, und sie wird zurzeit nicht vom Framework aufgerufen.  
  
##  <a name="a-nameonclosingmainframea--cwinappexonclosingmainframe"></a><a name="onclosingmainframe"></a>CWinAppEx::OnClosingMainFrame  
 Das Framework ruft diese Methode auf, bei der Verarbeitung eines Rahmenfensters `WM_CLOSE`.  
  
```  
virtual void OnClosingMainFrame(CFrameImpl* pFrameImpl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrameImpl`  
 Ein Zeiger auf ein `CFrameImpl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode speichert den Zustand des `pFrameImpl`.  
  
##  <a name="a-nameonviewdoubleclicka--cwinappexonviewdoubleclick"></a><a name="onviewdoubleclick"></a>CWinAppEx::OnViewDoubleClick  
 Ruft den benutzerdefinierten Befehl, der einer Ansicht zugeordnet ist, wenn der Benutzer auf eine beliebige Stelle in dieser Ansicht doppelklickt.  
  
```  
virtual BOOL OnViewDoubleClick(
    CWnd* pWnd,  
    int iViewId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf ein Objekt abgeleitet aus der [CView-Klasse](../../mfc/reference/cview-class.md).  
  
 [in] `iViewId`  
 Die Sicht-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `True`Wenn das Framework einen Befehl sucht. andernfalls False.  
  
### <a name="remarks"></a>Hinweise  
 Um benutzerdefinierte Verhalten zu unterstützen, müssen Sie diese Funktion aufrufen, beim Verarbeiten der `WM_LBUTTONDBLCLK` Nachricht. Diese Methode führt den Befehl, der die ID der vom zugeordneten `iViewId`. Weitere Informationen zu benutzerdefinierten Verhalten, finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).  
  
##  <a name="a-nameonworkspaceidlea--cwinappexonworkspaceidle"></a><a name="onworkspaceidle"></a>CWinAppEx::OnWorkspaceIdle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnWorkspaceIdle(CWnd*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CWnd*`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namepreloadstatea--cwinappexpreloadstate"></a><a name="preloadstate"></a>CWinAppEx::PreLoadState  
 Das Framework ruft diese Methode auf, unmittelbar bevor der Status der Anwendung aus der Registrierung geladen.  
  
```  
virtual void PreLoadState();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Verarbeitungsvorgänge ausführen, unmittelbar bevor das Framework Zustand der Anwendung geladen werden soll.  
  
##  <a name="a-namepresavestatea--cwinappexpresavestate"></a><a name="presavestate"></a>CWinAppEx::PreSaveState  
 Das Framework ruft diese Methode auf, unmittelbar bevor der Zustand der Anwendung gespeichert.  
  
```  
virtual void PreSaveState();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Verarbeitungsvorgänge ausführen, unmittelbar bevor das Framework den Anwendungsstatus gespeichert werden soll.  
  
##  <a name="a-namereloadwindowplacementa--cwinappexreloadwindowplacement"></a><a name="reloadwindowplacement"></a>CWinAppEx::ReloadWindowPlacement  
 Lädt die Größe und Position eines Fensters aus der Registrierung.  
  
```  
virtual BOOL ReloadWindowPlacement(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Rahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; 0, wenn die Last fehlgeschlagen, oder es keine Daten geladen wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Funktion [CWinAppEx::StoreWindowPlacement](#storewindowplacement) die Größe und Position eines Fensters in die Registrierung geschrieben.  
  
##  <a name="a-namesavecustomstatea--cwinappexsavecustomstate"></a><a name="savecustomstate"></a>CWinAppEx::SaveCustomState  
 Das Framework ruft diese Methode auf, nachdem der Status der Anwendung in der Registrierung gespeichert.  
  
```  
virtual void SaveCustomState();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn eine beliebige Verarbeitung erfolgen, nachdem die Anwendung den Status in der Registrierung gespeichert werden sollen. Standardmäßig bewirkt diese Methode nichts.  
  
##  <a name="a-namesavestatea--cwinappexsavestate"></a><a name="savestate"></a>CWinAppEx::SaveState  
 Zustand der Anwendung in die Windows-Registrierung geschrieben.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);

 
BOOL SaveState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSectionName`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `pFrameImpl`  
 Ein Zeiger auf ein `CFrameImpl` Objekt. Dieser Rahmen wird in der Windows-Registrierung gespeichert.  
  
 [in] `pFrame`  
 Ein Zeiger auf ein Fensterobjekt Frame. Dieser Rahmen wird in der Windows-Registrierung gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 `True`Bei Erfolg; `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode speichert den Zustand der Anwendung und alle Zustandsinformationen für die bereitgestellten Rahmenfenster. Wenn Sie ein Rahmenfenster nicht angeben, speichert die-Methode nur Zustand der Anwendung. Anwendungsinformationen umfasst die Statuswerte von der [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md), und die [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md).  
  
 Die `lpszSectionName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
##  <a name="a-namesetregistrybasea--cwinappexsetregistrybase"></a><a name="setregistrybase"></a>CWinAppEx::SetRegistryBase  
 Legt den Standardpfad für die Registrierung für die Anwendung fest.  
  
```  
LPCTSTR SetRegistryBase(LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSectionName`  
 Eine Zeichenfolge, die den Pfad eines Registrierungsschlüssels enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Pfad der Standardspeicherort für die Registrierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Alle Methoden der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) , die Zugriff auf die Registrierung Start an einem Standardspeicherort. Verwenden Sie diese Methode, um dieser Standardspeicherort für die Registrierung ändern. Verwendung [CWinAppEx::GetRegistryBase](#getregistrybase) den Standardspeicherort für die Registrierung abgerufen.  
  
##  <a name="a-nameshowpopupmenua--cwinappexshowpopupmenu"></a><a name="showpopupmenu"></a>CWinAppEx::ShowPopupMenu  
 Zeigt ein Popupmenü an.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    const CPoint& point,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiMenuResId`  
 Ein Menü-Ressourcen-ID.  
  
 [in] `point`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , der die Position des Menüs in Bildschirmkoordinaten angibt.  
  
 [in] `pWnd`  
 Ein Zeiger auf das Fenster, das Popupmenü besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie im Popupmenü erfolgreich angezeigt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeigt das Menü zugeordnete `uiMenuResId`.  
  
 Unterstützung von Popupmenüs, benötigen Sie ein [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt. Wenn Sie nicht initialisiert haben die `CContextMenuManager` Objekt `ShowPopupMenu` schlägt fehl.  
  
##  <a name="a-namestorewindowplacementa--cwinappexstorewindowplacement"></a><a name="storewindowplacement"></a>CWinAppEx::StoreWindowPlacement  
 Aufgerufen, um die Größe und Position für das Hauptrahmenfenster in die Registrierung geschrieben.  
  
```  
virtual BOOL StoreWindowPlacement(
    const CRect& rectNormalPosition,  
    int nFlags,  
    int nShowCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 Flags, die die Position eines minimierten Fensters und des Betriebssystems wie zwischen einem minimierten Fenster und eine wiederhergestellte Fenster wechselt.  
  
 [in] `nShowCmd`  
 Eine ganze Zahl, die den Anzeigezustand des Fensters angibt. Weitere Informationen zu den möglichen Werten finden Sie unter [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
 [in] `rectNormalPosition`  
 Ein Rechteck, das die Koordinaten der Hauptrahmenfenster enthält, wenn es in der wiederhergestellten Zustand ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig speichert MFC automatisch die Position und den Zustand vor dem Beenden der Anwendung im Hauptrahmenfenster. Diese Informationen werden in der Registrierung unter dem Schlüssel WindowPlacement am Standardspeicherort für die Registrierung für Ihre Anwendung gespeichert. Weitere Informationen zu den Standardspeicherort für die Registrierung Ihrer Anwendung, finden Sie unter [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
 Überschreiben Sie diese Methode, wenn Sie zusätzliche Informationen zu dem Hauptrahmenfenster speichern möchten.  
  
##  <a name="a-namewritebinarya--cwinappexwritebinary"></a><a name="writebinary"></a>CWinAppEx::WriteBinary  
 Binäre Daten in die Registrierung geschrieben.  
  
```  
BOOL WriteBinary(
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [in] `pData`  
 Die zu speichernden Daten.  
  
 [in] `nBytes`  
 Die Größe des `pData` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags, der unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
 Wenn der Schlüssel von angegeben `lpszEntry` vorhanden ist, diese Methode erstellt.  
  
##  <a name="a-namewriteinta--cwinappexwriteint"></a><a name="writeint"></a>CWinAppEx::WriteInt  
 Numerische Daten in die Registrierung geschrieben.  
  
```  
BOOL WriteInt(
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [in] `nValue`  
 Die zu speichernden Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
 Wenn der Schlüssel von angegeben `lpszEntry` vorhanden ist, diese Methode erstellt.  
  
##  <a name="a-namewriteobjecta--cwinappexwriteobject"></a><a name="writeobject"></a>CWinAppEx::WriteObject  
 Schreibt Daten aus der [CObject-Klasse](../../mfc/reference/cobject-class.md) in der Registrierung.  
  
```  
BOOL WriteObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den festzulegenden Wert enthält.  
  
 [in] `obj`  
 Ein Verweis auf `CObject` Daten, die die Methode gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schreibt den `obj` Daten auf den angegebenen Wert unter dem Registrierungsschlüssel Standard. Verwendung [CWinAppEx::GetRegistryBase](#getregistrybase) um den aktuellen Registrierungsschlüssel zu bestimmen.  
  
##  <a name="a-namewritesectionbinarya--cwinappexwritesectionbinary"></a><a name="writesectionbinary"></a>CWinAppEx::WriteSectionBinary  
 Binäre Daten schreibt auf einen Wert in der Registrierung.  
  
```  
BOOL WriteSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge mit dem Namen eines Registrierungsschlüssels  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den festzulegenden Wert enthält.  
  
 [in] `pData`  
 Die Daten in die Registrierung geschrieben.  
  
 [in] `nBytes`  
 Die Größe des `pData` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszSubSection` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
 Wenn der Schlüssel von angegeben `lpszEntry` vorhanden ist, diese Methode erstellt.  
  
##  <a name="a-namewritesectioninta--cwinappexwritesectionint"></a><a name="writesectionint"></a>CWinAppEx::WriteSectionInt  
 Numerische Daten in die Registrierung geschrieben.  
  
```  
BOOL WriteSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den festzulegenden Wert enthält.  
  
 [in] `nValue`  
 Die Daten in die Registrierung geschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der das den Standard-Registrierungsschlüssel für die Anwendung angefügt wird. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
 Wenn der Schlüssel von angegeben `lpszEntry` vorhanden ist, diese Methode erstellt.  
  
##  <a name="a-namewritesectionobjecta--cwinappexwritesectionobject"></a><a name="writesectionobject"></a>CWinAppEx::WriteSectionObject  
 Schreibt Daten aus der [CObject-Klasse](../../mfc/reference/cobject-class.md) auf einen bestimmten Registrierungswert.  
  
```  
BOOL WriteSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen der den festzulegenden Wert enthält.  
  
 [in] `obj`  
 Die zu speichernden Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase)bzw..  
  
 Wenn der Wert `lpszEntry` unter dem angegebenen Registrierungsschlüssel nicht vorhanden `lpszSubSection`, diese Methode erstellt den Wert.  
  
##  <a name="a-namewritesectionstringa--cwinappexwritesectionstring"></a><a name="writesectionstring"></a>CWinAppEx::WriteSectionString  
 Schreibt eine Zeichenfolge Daten mit einem Wert in der Registrierung.  
  
```  
BOOL WriteSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszSubSection`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den festzulegenden Wert enthält.  
  
 [in] `lpszValue`  
 Die Zeichenfolgendaten in die Registrierung geschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszSubSection` Parameter ist es sich nicht um einen absoluten Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für die Anwendung angefügt ist. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase)bzw..  
  
 Wenn der Wert `lpszEntry` existiert nicht unter `lpszSubSection`, diese Methode erstellt.  
  
##  <a name="a-namewritestringa--cwinappexwritestring"></a><a name="writestring"></a>CWinAppEx::WriteString  
 Zeichenfolgen, die in die Registrierung schreibt.  
  
```  
BOOL WriteString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszEntry`  
 Eine Zeichenfolge, die den Namen eines Registrierungsschlüssels enthält.  
  
 [in] `lpszValue`  
 Die zu speichernden Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszEntry` Parameter ist der Name eines Registrierungseintrags unter dem Standard-Registrierungsschlüssel für die Anwendung befindet. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](#getregistrybase) und [CWinAppEx::SetRegistryBase](#setregistrybase) bzw..  
  
 Wenn der Schlüssel von angegeben `lspzEntry` vorhanden ist, diese Methode erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager-Klasse](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md)

