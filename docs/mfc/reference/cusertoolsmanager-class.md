---
title: CUserToolsManager Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaa99952daf401132768d9be5d4c589b5fdbee52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376196"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager-Klasse
Verwaltet die Auflistung der [CUserTool Klasse](../../mfc/reference/cusertool-class.md) Objekte in einer Anwendung. Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Mithilfe des Objekts `CUserToolsManager` können Benutzer oder Entwickler der Anwendung neue Benutzertools hinzuzufügen. Es unterstützt die Ausführung der Befehle, die Benutzertools zugeordnet sind, und speichert außerdem Informationen über Benutzertools in der Windows-Registrierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Erstellt ein Objekt vom Typ `CUserToolsManager`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Erstellt ein neues benutzertool an.|  
|[CUserToolsManager::FindTool](#findtool)|Gibt den Zeiger auf die `CMFCUserTool` -Objekt, das eine angegebene Befehls-ID zugeordnet ist|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Gibt die Ressourcen-ID, die mit zugeordnetem der **Argumente** Menü auf die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetDefExt](#getdefext)|Gibt die standarderweiterung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetFilter](#getfilter)|Gibt der dem Dateifilter, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Gibt die Ressourcen-ID, die mit zugeordnetem der **Ausgangsverzeichnis** Menü auf die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Gibt die maximale Anzahl von Benutzertools zugeordnet werden kann, die in der Anwendung zurück.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Gibt die Befehls-ID des Elementplatzhalters Menü für Benutzertools zurück.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Gibt einen Verweis auf die Liste der Benutzertools zurück.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Führt eine Anwendung mit der benutzertool, das eine angegebene Befehls-ID wurde|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Bestimmt, ob eine Befehls-ID ein benutzertool zugeordnet ist.|  
|[CUserToolsManager::LoadState](#loadstate)|Lädt Informationen über Benutzertools in der Windows-Registrierung.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Verschiebt den angegebenen Benutzer-Tool in die Liste der Benutzertools.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Verschiebt den angegebenen Benutzer-Tool nach oben in der Liste der Benutzertools.|  
|[CUserToolsManager::RemoveTool](#removetool)|Entfernt den angegebenen Benutzer-Tool aus der Anwendung an.|  
|[CUserToolsManager::SaveState](#savestate)|Speichert Informationen über Benutzertools in der Windows-Registrierung.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Gibt die Erweiterung an Standardeinstellung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** Registerkarte von der **anpassen** (Dialogfeld).|  
|[CUserToolsManager::SetFilter](#setfilter)|Gibt an, die Datei filtern, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).|  
  
## <a name="remarks"></a>Hinweise  
 Um Benutzertools in Ihre Anwendung integrieren, müssen Sie folgende Aktionen ausführen:  
  
 1. Reservieren Sie ein Menüelement und eine zugeordnete Befehls-ID für ein Menüeintrag des Benutzer-Tool.  
  
 2. Reservieren Sie eine sequenzielle Befehls-ID für jedes benutzertool, die ein Benutzer in Ihrer Anwendung definieren können.  
  
 3. Rufen Sie die [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Methode, und geben Sie die folgenden Parameter: Menü Befehls-ID, ersten Benutzer Tool Befehls-ID und letzten Benutzer Tool Befehls-ID.  
  
 Es darf nur eine globale `CUserToolsManager` Objekt pro Anwendung.  
  
 Ein Beispiel dafür Benutzertools finden Sie das Beispielprojekt VisualStudioDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie einen Verweis zum Abrufen einer `CUserToolsManager` Objekt und wie Sie neue Benutzertools zu erstellen. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>  CUserToolsManager::CreateNewTool  
 Erstellt ein neues benutzertool an.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte User-Tool oder `NULL` , wenn die Anzahl der Benutzertools das Maximum überschritten hat. Der zurückgegebene Typ entspricht der Typ, der an übergebene `CWinAppEx::EnableUserTools` als die `pToolRTC` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht das erste verfügbare Menübefehl-ID in den Bereich, der im Aufruf angegeben wird [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) und weist das Tool, das diese ID.  
  
 Die Methode schlägt fehl, wenn die Anzahl der Tools auf das Maximum erreicht hat. Dies tritt auf, wenn alle Befehls-IDs innerhalb des Bereichs Benutzertools zugeordnet sind. Sie können die maximale Anzahl der Tools abrufen, durch den Aufruf [CUserToolsManager::GetMaxTools](#getmaxtools). Sie erhalten Zugriff auf die Liste der Tools durch Aufrufen der [CUserToolsManager::GetUserTools](#getusertools) Methode.  
  
##  <a name="cusertoolsmanager"></a>  CUserToolsManager::CUserToolsManager  
 Erstellt ein Objekt vom Typ `CUserToolsManager`. Jede Anwendung benötigen darf höchstens eine Benutzer-Tools-Manager.  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdToolsDummy`  
 Eine ganze Zahl ohne Vorzeichen, die das Framework für die Befehls-ID des Benutzers im Menü Extras als Platzhalter verwendet.  
  
 [in] `uiCmdFirst`  
 Die Befehls-ID für den ersten Benutzer Tool-Befehl.  
  
 [in] `uiCmdLast`  
 Die Befehls-ID für den letzten Benutzer Tool-Befehl.  
  
 [in] `pToolRTC`  
 Die Klasse, die [CUserToolsManager::CreateNewTool](#createnewtool) erstellt. Durch die Verwendung dieser Klasse können Sie einen abgeleiteten Typ von [CUserTool Klasse](../../mfc/reference/cusertool-class.md) statt die standardmäßige Implementierung.  
  
 [in] `uArgMenuID`  
 Die im Menü-Ressourcen-ID des Popupmenüs Argumente.  
  
 [in] `uInitDirMenuID`  
 Der Menü-Ressourcen-ID, der das Ausgangsverzeichnis Popupmenü werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diesen Konstruktor nicht. Rufen Sie stattdessen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) auf Benutzertools zu aktivieren, und rufen [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) um einen Zeiger auf die `CUserToolsManager`. Weitere Informationen finden Sie unter [benutzerdefinierte Tools](../../mfc/user-defined-tools.md).  
  
##  <a name="findtool"></a>  CUserToolsManager::FindTool  
 Gibt den Zeiger auf die [CUserTool Klasse](../../mfc/reference/cusertool-class.md) -Objekt, das eine angegebene Befehls-ID zugeordnet ist  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Ein Bezeichner für den Menü-Befehl.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CUserTool Klasse](../../mfc/reference/cusertool-class.md) oder `CUserTool`-abgeleitetes Objekt aus, wenn erfolgreich; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `FindTool` ist erfolgreich, der zurückgegebene Typ entspricht der Typ des der `pToolRTC` Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getargumentsmenuid"></a>  CUserToolsManager::GetArgumentsMenuID  
 Gibt die Ressourcen-ID, die mit zugeordnetem der **Argumente** Menü auf die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld).  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bezeichner des eine Menüressource.  
  
### <a name="remarks"></a>Hinweise  
 Die `uArgMenuID` Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) gibt die ID der Ressource.  
  
##  <a name="getdefext"></a>  CUserToolsManager::GetDefExt  
 Gibt die standarderweiterung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die `CString` Objekt, das die Erweiterung enthält.  
  
##  <a name="getfilter"></a>  CUserToolsManager::GetFilter  
 Gibt der dem Dateifilter, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die `CString` -Objekt, das den Filter enthält.  
  
##  <a name="getinitialdirmenuid"></a>  CUserToolsManager::GetInitialDirMenuID  
 Gibt die Ressourcen-ID, die mit zugeordnetem der **Ausgangsverzeichnis** Menü auf die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld).  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für den Menü-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene ID wird angegeben, der `uInitDirMenuID` Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getmaxtools"></a>  CUserToolsManager::GetMaxTools  
 Gibt die maximale Anzahl von Benutzertools zugeordnet werden kann, die in der Anwendung zurück.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Benutzertools, die zugeordnet werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die maximale Anzahl der Tools abrufen, die in der Anwendung zugeordnet werden kann. Diese Zahl ist die Anzahl von IDs im Bereich zwischen der `uiCmdFirst` über die `uiCmdLast` Parameter, die Sie übergeben [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="gettoolsentrycmd"></a>  CUserToolsManager::GetToolsEntryCmd  
 Gibt die Befehls-ID des Elementplatzhalters Menü für Benutzertools zurück.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID des Platzhalters.  
  
### <a name="remarks"></a>Hinweise  
 Um Benutzertools zu aktivieren, rufen Sie [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Die `uiCmdToolsDummy` Parameter gibt die Befehls-ID des Befehls Eintrag Tools. Diese Methode gibt die Tools Eintrag Befehls-ID. Wo diese ID in einem Menü verwendet wird, wird es durch die Liste der Benutzertools ersetzt, wenn das Menü angezeigt wird.  
  
##  <a name="getusertools"></a>  CUserToolsManager::GetUserTools  
 Gibt einen Verweis auf die Liste der Benutzertools zurück.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein konstanter Verweis auf eine [CObList Klasse](../../mfc/reference/coblist-class.md) Objekt, das eine Liste der Benutzertools enthält.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Methode zum Abrufen einer Liste der Benutzer tools, die [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) -Objekt verwaltet. Jedes benutzertool ist ein Objekt vom Typ dargestellte [CUserTool Klasse](../../mfc/reference/cusertool-class.md) oder ein abgeleiteter Typ von `CUserTool`. Der Typ wird angegeben, indem die `pToolRTC` -Parameter beim Aufrufen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools zu aktivieren.  
  
##  <a name="invoketool"></a>  CUserToolsManager::InvokeTool  
 Führt eine Anwendung mit der benutzertool, das eine angegebene Befehls-ID wurde  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Die Menübefehl-ID mit dem Benutzer zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der zugeordnete benutzertool Befehl erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Methode zum Ausführen einer Anwendung, die dem Benutzer zugeordneten tool, hat die Befehls-ID gemäß `uiCmdId`.  
  
##  <a name="isusertoolcmd"></a>  CUserToolsManager::IsUserToolCmd  
 Bestimmt, ob eine Befehls-ID ein benutzertool zugeordnet ist.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Eine Befehls-ID des Menüelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine angegebene Befehls-ID ein benutzertool zugeordnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, ob die angegebenen Befehls-ID in der Befehls-ID-Bereich. Wenn Sie aufrufen, geben Sie den Bereich [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools zu aktivieren.  
  
##  <a name="loadstate"></a>  CUserToolsManager::LoadState  
 Lädt Informationen über Benutzertools in der Windows-Registrierung.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Pfad der Windows-Registrierungsschlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode lädt den Zustand der `CUserToolsManager` Objekt aus der Windows-Registrierung.  
  
 In der Regel wird diese Methode nicht direkt aufrufen. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) wird bei der Initialisierung des Arbeitsbereich aufgerufen.  
  
##  <a name="movetooldown"></a>  CUserToolsManager::MoveToolDown  
 Verschiebt den angegebenen Benutzer-Tool in die Liste der Benutzertools.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTool`  
 Gibt das User-Tool zu verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der benutzertool wurde erfolgreich nach unten verschoben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode fehlschlägt, wenn das Tool, das `pTool` gibt an, befindet sich nicht in der internen Liste oder wenn das Tool zuletzt in der Liste angezeigt wird.  
  
##  <a name="movetoolup"></a>  CUserToolsManager::MoveToolUp  
 Verschiebt den angegebenen Benutzer-Tool nach oben in der Liste der Benutzertools.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTool`  
 Gibt das User-Tool zu verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der benutzertool wurde erfolgreich nach oben verschoben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode fehlschlägt, wenn das Tool, das `pTool` befindet sich nicht in der internen Liste angegeben wird oder wenn Sie das Tool das erste Tool-Element in der Liste.  
  
##  <a name="removetool"></a>  CUserToolsManager::RemoveTool  
 Entfernt den angegebenen Benutzer-Tool aus der Anwendung an.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pTool`  
 Ein Zeiger auf ein benutzertool entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Tool erfolgreich entfernt wird. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Tool erfolgreich entfernt wird, wird diese Methode löscht `pTool`.  
  
##  <a name="savestate"></a>  CUserToolsManager::SaveState  
 Speichert Informationen über Benutzertools in der Windows-Registrierung.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad zu den Windows-Registrierungsschlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand erfolgreich gespeichert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode speichert den aktuellen Status des der `CUserToolsManager` Objekt in der Windows-Registrierung.  
  
 In der Regel ist, Sie müssen nicht direkt aufrufen dieser Methode [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) wird automatisch als Teil des Serialisierungsprozesses Arbeitsbereich der Anwendung aufgerufen.  
  
##  <a name="setdefext"></a>  CUserToolsManager::SetDefExt  
 Gibt die Erweiterung an Standardeinstellung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** Registerkarte von der **anpassen** (Dialogfeld).  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDefExt`  
 Eine Textzeichenfolge, die die standardmäßige Dateinamenerweiterung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine Standard-Dateinamenerweiterung im Angeben der **Datei öffnen** (Dialogfeld), der angezeigt wird, wenn der Benutzer eine Anwendung mit dem benutzertool zuordnen auswählt. Der Standardwert ist "Exe".  
  
##  <a name="setfilter"></a>  CUserToolsManager::SetFilter  
 Gibt an, die Datei filtern, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet, der **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** (Dialogfeld).  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strFilter`  
 Gibt den Filter.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CUserTool-Klasse](../../mfc/reference/cusertool-class.md)
