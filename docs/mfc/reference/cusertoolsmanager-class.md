---
title: Klasse CUserToolsManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CUserToolsManager class
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
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
ms.openlocfilehash: 0b82adf0f9eba5ee334ada2c169546f27894c1dd
ms.lasthandoff: 02/24/2017

---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager-Klasse
Verwaltet die Auflistung der [CUserTool Klasse](../../mfc/reference/cusertool-class.md) Objekte in einer Anwendung. Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Mithilfe des Objekts `CUserToolsManager` können Benutzer oder Entwickler der Anwendung neue Benutzertools hinzuzufügen. Es unterstützt die Ausführung der Befehle, die Benutzertools zugeordnet sind, und speichert außerdem Informationen über Benutzertools in der Windows-Registrierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Erstellt ein Objekt vom Typ `CUserToolsManager`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Erstellt ein neues Tool.|  
|[CUserToolsManager::FindTool](#findtool)|Gibt den Zeiger auf das `CMFCUserTool` -Objekt, das eine angegebene Befehls-ID zugeordnet ist|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Gibt die Ressourcen-ID, die zugeordnet ist die **Argumente** Menü auf die **Tools** auf der Registerkarte der **anpassen** Dialogfeld.|  
|[CUserToolsManager::GetDefExt](#getdefext)|Gibt die standarderweiterung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetFilter](#getfilter)|Gibt den Dateifilter zurück, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** (Dialogfeld).|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Gibt die Ressourcen-ID, die zugeordnet ist die **Ausgangsverzeichnis** Menü auf die **Tools** auf der Registerkarte der **anpassen** Dialogfeld.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Gibt die maximale Anzahl von Benutzertools, die zugeordnet werden können in der Anwendung zurück.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Gibt die Befehls-ID des Menü Elementplatzhalters für Benutzertools zurück.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Gibt einen Verweis auf die Liste der Benutzertools zurück.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Führt eine Anwendung gehörenden Benutzer, die eine angegebene ID verfügt.|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Bestimmt, ob eine Befehls-ID ein Tool zugeordnet ist.|  
|[CUserToolsManager::LoadState](#loadstate)|Lädt Informationen über Benutzertools in der Windows-Registrierung.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Verschiebt die angegebene Benutzer-Tool in der Liste der Benutzer.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Verschiebt die angegebene Benutzer-Tool in der Liste der Benutzer.|  
|[CUserToolsManager::RemoveTool](#removetool)|Entfernt das Tool für die angegebenen Benutzer aus der Anwendung.|  
|[CUserToolsManager::SaveState](#savestate)|Informationen über Benutzertools in der Windows-Registrierung gespeichert.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Gibt die standarderweiterung, die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** Dialogfeld.|  
|[CUserToolsManager::SetFilter](#setfilter)|Gibt an, die Datei zu filtern, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** Dialogfeld.|  
  
## <a name="remarks"></a>Hinweise  
 Benutzertools in Ihre Anwendung einbinden, müssen Sie folgende Aktionen ausführen:  
  
 1. Reservieren Sie ein Menüelement und einem zugeordneten Befehls-ID für einen Benutzer Tool Menüeintrag.  
  
 2. Reservieren Sie eine sequenzielle Befehls-ID für jedes benutzertool, die ein Benutzer in Ihrer Anwendung definieren können.  
  
 3. Rufen Sie die [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Methode, und geben Sie die folgenden Parameter: Menü Befehls-ID, ersten Benutzer Tool Befehls-ID und letzten Benutzer Tool Befehls-ID.  
  
 Sollte es nicht nur eine globale `CUserToolsManager` -Objekt pro Anwendung.  
  
 Ein Beispiel für Benutzertools finden Sie unter das VisualStudioDemo-Beispielprojekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Abrufen eines Verweises auf ein `CUserToolsManager` Objekt und wie Sie neue Benutzertools erstellen. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#38;](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 Erstellt ein neues Tool.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte User-Tool oder `NULL` , wenn die Anzahl der Benutzertools das Maximum überschritten hat. Der zurückgegebene Typ entspricht der Typ, der an `CWinAppEx::EnableUserTools` als die `pToolRTC` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht die erste verfügbare Menübefehl-ID im Bereich, der im Aufruf von [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) und weist dem Tool, das diese ID.  
  
 Die Methode schlägt fehl, wenn die Anzahl der Tools das Maximum erreicht hat. Dies tritt auf, wenn alle Befehls-IDs innerhalb des Bereichs Benutzertools zugeordnet sind. Sie können die maximale Anzahl von Tools abrufen, durch Aufrufen von [CUserToolsManager::GetMaxTools](#getmaxtools). Sie erhalten Zugriff auf die Liste der Tools durch Aufrufen der [CUserToolsManager::GetUserTools](#getusertools) Methode.  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 Erstellt ein Objekt vom Typ `CUserToolsManager`. Jede Anwendung muss höchstens einen Benutzer Tools Manager haben.  
  
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
 Eine ganze Zahl ohne Vorzeichen, die das Framework als Platzhalter für die Befehls-ID des Menüs Extras Benutzer verwendet.  
  
 [in] `uiCmdFirst`  
 Die Befehls-ID für den ersten Benutzer Tool-Befehl.  
  
 [in] `uiCmdLast`  
 Die Befehls-ID für den letzten Befehl des User-Tool.  
  
 [in] `pToolRTC`  
 Die Klasse, die [CUserToolsManager::CreateNewTool](#createnewtool) erstellt. Mithilfe dieser Klasse können Sie einen abgeleiteten Typ von [CUserTool Klasse](../../mfc/reference/cusertool-class.md) anstelle der Standardimplementierung.  
  
 [in] `uArgMenuID`  
 Der Menü-Ressourcen-ID des Popupmenüs Argumente.  
  
 [in] `uInitDirMenuID`  
 Der Menü-Ressourcen-ID des anfänglichen Verzeichnisses Popupmenüs.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diesen Konstruktor nicht. Rufen Sie stattdessen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) , Benutzertools aktivieren, und rufen [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) ein Zeiger auf die `CUserToolsManager`. Weitere Informationen finden Sie unter [benutzerdefinierte Tools](../../mfc/user-defined-tools.md).  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 Gibt den Zeiger auf die [CUserTool Klasse](../../mfc/reference/cusertool-class.md) -Objekt, das eine angegebene Befehls-ID zugeordnet ist  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Ein Bezeichner für den Menü-Befehl.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CUserTool Klasse](../../mfc/reference/cusertool-class.md) oder `CUserTool`-abgeleitetes Objekt, wenn erfolgreich, andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `FindTool` ist erfolgreich, der zurückgegebene Typ entspricht der Typ des der `pToolRTC` Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 Gibt die Ressourcen-ID, die zugeordnet ist die **Argumente** Menü auf die **Tools** auf der Registerkarte der **anpassen** Dialogfeld.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bezeichner einer Ressource im Menü.  
  
### <a name="remarks"></a>Hinweise  
 Die `uArgMenuID` Parameter der [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) gibt die ID der Ressource.  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 Gibt die standarderweiterung, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** (Dialogfeld).  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die `CString` -Objekt, das die Erweiterung enthält.  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 Gibt den Dateifilter zurück, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** (Dialogfeld).  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die `CString` -Objekt, das den Filter enthält.  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 Gibt die Ressourcen-ID, die zugeordnet ist die **Ausgangsverzeichnis** Menü auf die **Tools** auf der Registerkarte der **anpassen** Dialogfeld.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für den Menü-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene ID wird angegeben, der `uInitDirMenuID` Parameter der [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 Gibt die maximale Anzahl von Benutzertools, die zugeordnet werden können in der Anwendung zurück.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Benutzertools, die zugeordnet werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die maximale Anzahl von Tools abrufen, die in der Anwendung zugeordnet werden kann. Diese Zahl ist die Anzahl von IDs im Bereich von der `uiCmdFirst` über die `uiCmdLast` Parameter, die an übergeben [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 Gibt die Befehls-ID des Menü Elementplatzhalters für Benutzertools zurück.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID des Platzhalters.  
  
### <a name="remarks"></a>Hinweise  
 Um Benutzertools, rufen Sie [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Die `uiCmdToolsDummy` Parameter gibt die Befehls-ID des Befehls Eintrag Tools. Diese Methode gibt die Tools Eintrag Befehls-ID. Wo diese ID in einem Menü verwendet wird, wird sie durch die Liste der Benutzertools ersetzt, wenn das Menü angezeigt wird.  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 Gibt einen Verweis auf die Liste der Benutzertools zurück.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein konstanter Verweis auf eine [CObList-Klasse](../../mfc/reference/coblist-class.md) -Objekt, das eine Liste der Benutzertools enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen einer Liste von tools, die [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) -Objekt verwaltet. Jedes Tool, das durch ein Objekt des Typs dargestellt wird [CUserTool Klasse](../../mfc/reference/cusertool-class.md) oder einen abgeleiteten Typ von `CUserTool`. Der Typ wird angegeben, indem die `pToolRTC` -Parameter beim Aufrufen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools aktivieren.  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 Führt eine Anwendung gehörenden Benutzer, die eine angegebene ID verfügt.  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Der Menübefehl-ID mit dem Benutzer zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer zugeordnete Befehl erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Methode ausführen eine Anwendung, die dem Benutzer zugeordneten tool, hat die Befehls-ID, die durch angegebene `uiCmdId`.  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 Bestimmt, ob eine Befehls-ID ein Tool zugeordnet ist.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Eine Befehls-ID des Menüelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine angegebene Befehls-ID ein Tool zugeordnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, ob die angegebene Befehls-ID in der Befehls-ID-Bereich. Wenn Sie aufrufen, geben Sie den Bereich [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools aktivieren.  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
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
  
 In der Regel wird diese Methode nicht direkt aufrufen. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) wird als Teil des Arbeitsbereichs Initialisierungsprozess aufgerufen.  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 Verschiebt die angegebene Benutzer-Tool in der Liste der Benutzer.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTool`  
 Gibt das benutzertool "zu verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Tool, das erfolgreich, nach unten verschoben wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode schlägt fehl, wenn das Tool, das `pTool` gibt ist nicht in der internen Liste oder das Tool in der Liste an letzter Stelle ist.  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 Verschiebt die angegebene Benutzer-Tool in der Liste der Benutzer.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTool`  
 Gibt das benutzertool "zu verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Tool, das erfolgreich, um verschoben wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode schlägt fehl, wenn das Tool, das `pTool` Parameter gibt, ist nicht in der internen Liste oder das Tool das erste Tool-Element in der Liste ist.  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 Entfernt das Tool für die angegebenen Benutzer aus der Anwendung.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pTool`  
 Ein Zeiger auf ein Tool entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Tool erfolgreich entfernt wurde. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Tool erfolgreich entfernt wurde, wird diese Methode löscht `pTool`.  
  
##  <a name="savestate"></a>CUserToolsManager::SaveState  
 Informationen über Benutzertools in der Windows-Registrierung gespeichert.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad zu den Windows-Registrierungsschlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand erfolgreich gespeichert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode speichert den aktuellen Zustand von der `CUserToolsManager` Objekt in der Windows-Registrierung.  
  
 In der Regel, Sie müssen nicht direkt aufrufen dieser Methode [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) wird automatisch als Teil des Serialisierungsprozesses Arbeitsbereich der Anwendung aufgerufen.  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 Gibt die standarderweiterung, die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** Dialogfeld.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDefExt`  
 Eine Textzeichenfolge, die die standarddateinamenerweiterung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Angeben der standardmäßige Erweiterung in der **Datei öffnen** im Dialogfeld angezeigt wird, bei der Auswahl einer Anwendung, die mit dem benutzertool zugeordnet. Der Standardwert ist "Exe".  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 Gibt an, die Datei zu filtern, die die **Datei öffnen** (Dialogfeld) ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** auf der Registerkarte der **anpassen** Dialogfeld.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strFilter`  
 Gibt den Filter an.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CUserTool-Klasse](../../mfc/reference/cusertool-class.md)

