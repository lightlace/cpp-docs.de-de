---
title: CUserToolsManager-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 405260d4bc2f7cdf163dbd7a00f342b8afc87d48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668112"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager-Klasse

Verwaltet die Auflistung der [CUserTool-Klasse](../../mfc/reference/cusertool-class.md) Objekte in einer Anwendung. Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Mithilfe des Objekts `CUserToolsManager` können Benutzer oder Entwickler der Anwendung neue Benutzertools hinzuzufügen. Es unterstützt die Ausführung der Befehle, die Benutzertools zugeordnet sind, und speichert außerdem Informationen über Benutzertools in der Windows-Registrierung.

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
|[CUserToolsManager::CreateNewTool](#createnewtool)|Erstellt ein neues Tool.|
|[CUserToolsManager::FindTool](#findtool)|Gibt den Zeiger auf die `CMFCUserTool` -Objekt, das eine angegebene Befehls-ID zugeordnet ist|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Gibt die Ressourcen-ID, die zugeordnet wird die **Argumente** Menü auf der **Tools** auf der Registerkarte die **anpassen** Dialogfeld.|
|[CUserToolsManager::GetDefExt](#getdefext)|Lautet der standarderweiterung zurückgibt, die die **Datei öffnen** Dialogfeld ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **Anpassen** Dialogfeld.|
|[CUserToolsManager::GetFilter](#getfilter)|Gibt zurück, der dem Dateifilter der **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** Dialogfeld.|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Gibt die Ressourcen-ID, die zugeordnet wird die **Ausgangsverzeichnis** Menü auf der **Tools** auf der Registerkarte die **anpassen** Dialogfeld.|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Gibt die maximale Anzahl von Benutzertools, die zugeordnet werden können in der Anwendung zurück.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Gibt die Befehls-ID, der den Menü-Element-Platzhalter für Benutzertools zurück.|
|[CUserToolsManager::GetUserTools](#getusertools)|Gibt einen Verweis auf die Liste der Benutzertools zurück.|
|[CUserToolsManager::InvokeTool](#invoketool)|Führt eine Anwendung, die die benutzertool, das eine angegebene Befehls-ID wurde zugeordnet|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Bestimmt, ob eine Befehls-ID ein Tool zugeordnet ist.|
|[CUserToolsManager::LoadState](#loadstate)|Lädt Informationen über Benutzertools in der Windows-Registrierung.|
|[CUserToolsManager::MoveToolDown](#movetooldown)|Verschiebt Sie in der Liste der Tools für das angegebene Benutzer-Tool nach unten.|
|[CUserToolsManager::MoveToolUp](#movetoolup)|Verschiebt Sie in der Liste der Tools für das angegebene Benutzer-Tool nach oben.|
|[CUserToolsManager::RemoveTool](#removetool)|Entfernt das Tool für die angegebenen Benutzer aus der Anwendung an.|
|[CUserToolsManager::SaveState](#savestate)|Speichert Informationen über Benutzertools in der Windows-Registrierung.|
|[CUserToolsManager::SetDefExt](#setdefext)|Gibt an, die standarderweiterung, die die **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** Registerkarte von der **anpassen** Dialogfeld.|
|[CUserToolsManager::SetFilter](#setfilter)|Gibt an, die Datei filtern, die die **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **Anpassen** Dialogfeld.|

## <a name="remarks"></a>Hinweise

Um Benutzertools in Ihrer Anwendung zu integrieren, müssen Sie folgende Aktionen ausführen:

1. Reservieren Sie ein Menüelement und eine zugeordnete Befehls-ID für ein Tool im Menü-Benutzereintrag.

2. Reservieren Sie eine sequenzielle Befehls-ID für jedes benutzertool, die ein Benutzer in Ihrer Anwendung definieren können.

3. Rufen Sie die [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Methode, und geben Sie die folgenden Parameter: Menü Befehls-ID, ersten Benutzer Tool Befehls-ID und letzten Benutzer Tool Befehls-ID.

Es muss nur eine globale `CUserToolsManager` -Objekt pro Anwendung.

Ein Beispiel für Benutzertools finden Sie das Beispielprojekt VisualStudioDemo.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Abrufen eines Verweises auf eine `CUserToolsManager` Objekt und wie Sie neue Benutzertools zu erstellen. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Anforderungen

**Header:** afxusertoolsmanager.h

##  <a name="createnewtool"></a>  CUserToolsManager::CreateNewTool

Erstellt ein neues Tool.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den neu erstellten benutzertool oder NULL, wenn die Anzahl der Tools für das Maximum überschritten hat. Der zurückgegebene Typ entspricht der Typ, der an übergebene `CWinAppEx::EnableUserTools` als die *pToolRTC* Parameter.

### <a name="remarks"></a>Hinweise

Diese Methode sucht die erste verfügbare-Menübefehls-ID in den Bereich, der im Aufruf angegeben wird [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) und weist dem benutzertool diese ID.

Die Methode schlägt fehl, wenn die Anzahl der Tools auf das Maximum erreicht hat. Dies tritt auf, wenn alle Befehls-IDs innerhalb des Bereichs Benutzertools zugeordnet sind. Sie können die maximale Anzahl von Tools abrufen, durch den Aufruf [CUserToolsManager::GetMaxTools](#getmaxtools). Sie erhalten Zugriff auf die Liste der Tools durch Aufrufen der [CUserToolsManager::GetUserTools](#getusertools) Methode.

##  <a name="cusertoolsmanager"></a>  CUserToolsManager::CUserToolsManager

Erstellt ein Objekt vom Typ `CUserToolsManager`. Jede Anwendung muss es sich um höchstens einen Benutzer Tools Manager haben.

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

*uiCmdToolsDummy*<br/>
[in] Eine ganze Zahl ohne Vorzeichen, die das Framework als Platzhalter für die Befehls-ID des Benutzers im Menü Extras verwendet.

*uiCmdFirst*<br/>
[in] Die Befehls-ID für den ersten Befehl des User-Tool.

*uiCmdLast*<br/>
[in] Die Befehls-ID für den letzten Benutzer Tool-Befehl.

*pToolRTC*<br/>
[in] Die Klasse, die [CUserToolsManager::CreateNewTool](#createnewtool) erstellt. Durch die Verwendung dieser Klasse können Sie einen abgeleiteten Typ von [CUserTool-Klasse](../../mfc/reference/cusertool-class.md) anstelle der Standardimplementierung.

*uArgMenuID*<br/>
[in] Der Menü-Ressourcen-ID des Popupmenüs Argumente.

*uInitDirMenuID*<br/>
[in] Der Menü-Ressourcen-ID des Popupmenüs Ausgangsverzeichnis.

### <a name="remarks"></a>Hinweise

Rufen Sie diesen Konstruktor nicht. Rufen Sie stattdessen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) , Benutzertools aktivieren, und rufen [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) einen Zeiger zum Abrufen der `CUserToolsManager`. Weitere Informationen finden Sie unter [benutzerdefinierte Tools](../../mfc/user-defined-tools.md).

##  <a name="findtool"></a>  CUserToolsManager::FindTool

Gibt den Zeiger auf die [CUserTool-Klasse](../../mfc/reference/cusertool-class.md) -Objekt, das eine angegebene Befehls-ID zugeordnet ist

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parameter

*uiCmdId*<br/>
[in] Ein Bezeichner für den Menü-Befehl.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CUserTool-Klasse](../../mfc/reference/cusertool-class.md) oder `CUserTool`-abgeleitetes Objekt aus, wenn erfolgreich, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn `FindTool` ist erfolgreich, der zurückgegebene Typ entspricht der Typ des der *pToolRTC* Parameter, um [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getargumentsmenuid"></a>  CUserToolsManager::GetArgumentsMenuID

Gibt die Ressourcen-ID, die zugeordnet wird die **Argumente** Menü auf der **Tools** auf der Registerkarte die **anpassen** Dialogfeld.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Rückgabewert

Der Bezeichner einer Ressource im Menü.

### <a name="remarks"></a>Hinweise

Die *uArgMenuID* Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) gibt die ID der Ressource.

##  <a name="getdefext"></a>  CUserToolsManager::GetDefExt

Lautet der standarderweiterung zurückgibt, die die **Datei öffnen** Dialogfeld ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **Anpassen** Dialogfeld.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die `CString` -Objekt, das die Erweiterung enthält.

##  <a name="getfilter"></a>  CUserToolsManager::GetFilter

Gibt zurück, der dem Dateifilter der **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte die **Anpassen** Dialogfeld.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die `CString` -Objekt, das den Filter enthält.

##  <a name="getinitialdirmenuid"></a>  CUserToolsManager::GetInitialDirMenuID

Gibt die Ressourcen-ID, die zugeordnet wird die **Ausgangsverzeichnis** Menü auf der **Tools** auf der Registerkarte die **anpassen** Dialogfeld.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Bezeichner für den Menü-Ressource.

### <a name="remarks"></a>Hinweise

Die zurückgegebene ID wird angegeben, der *uInitDirMenuID* Parameter [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getmaxtools"></a>  CUserToolsManager::GetMaxTools

Gibt die maximale Anzahl von Benutzertools, die zugeordnet werden können in der Anwendung zurück.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von Benutzertools, die zugeordnet werden können.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die maximale Anzahl von Tools abrufen, die in der Anwendung zugeordnet werden können. Diese Zahl ist die Anzahl von IDs im Bereich von der *UiCmdFirst* über die *UiCmdLast* Parameter, die Sie übergeben [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="gettoolsentrycmd"></a>  CUserToolsManager::GetToolsEntryCmd

Gibt die Befehls-ID, der den Menü-Element-Platzhalter für Benutzertools zurück.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Rückgabewert

Die Befehls-ID des Platzhalters.

### <a name="remarks"></a>Hinweise

Um Benutzertools zu aktivieren, rufen Sie [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Die *UiCmdToolsDummy* Parameter gibt an, die Befehls-ID des Befehls Eintrag Tools. Diese Methode gibt zurück, die Tools-Eintrag-Befehls-ID. Wo diese ID in einem Menü verwendet wird, wird er von der Liste der Tools für ersetzt, wenn das Menü wird angezeigt.

##  <a name="getusertools"></a>  CUserToolsManager::GetUserTools

Gibt einen Verweis auf die Liste der Benutzertools zurück.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Rückgabewert

Einen konstanten Verweis auf eine [CObList-Klasse](../../mfc/reference/coblist-class.md) Objekt, das eine Liste der Benutzertools enthält.

### <a name="remarks"></a>Hinweise

Aufruf dieser Methode zum Abrufen einer Liste der tools, die [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) -Objekt verwaltet. Jedes benutzertool wird durch ein Objekt des Typs dargestellt [CUserTool-Klasse](../../mfc/reference/cusertool-class.md) oder ein abgeleiteter Typ von `CUserTool`. Der Typ wird angegeben, indem die *pToolRTC* -Parameter beim Aufrufen [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools zu aktivieren.

##  <a name="invoketool"></a>  CUserToolsManager::InvokeTool

Führt eine Anwendung, die die benutzertool, das eine angegebene Befehls-ID wurde zugeordnet

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Parameter

*uiCmdId*<br/>
[in] Die Menübefehl-ID mit dem benutzertool verknüpft ist.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der zugeordnete benutzertool Befehl erfolgreich ausgeführt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Aufruf dieser Methode, die eine Anwendung, die dem Benutzer zugeordneten Tools, hat die Befehls-ID gemäß *UiCmdId*.

##  <a name="isusertoolcmd"></a>  CUserToolsManager::IsUserToolCmd

Bestimmt, ob eine Befehls-ID ein Tool zugeordnet ist.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parameter

*uiCmdId*<br/>
[in] Eine Befehls-ID des Menüelements.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn ein bestimmter Befehl ID zugeordnet ist ein Tool; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode überprüft, ob die angegebene Befehls-ID in der Befehls-ID-Bereich ist. Wenn Sie aufrufen, geben Sie den Bereich [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Benutzertools zu aktivieren.

##  <a name="loadstate"></a>  CUserToolsManager::LoadState

Lädt Informationen über Benutzertools in der Windows-Registrierung.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Der Pfad des Windows-Registrierungsschlüssels.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Zustand erfolgreich geladen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode lädt den Zustand der der `CUserToolsManager` Objekt aus der Windows-Registrierung.

In der Regel wird diese Methode nicht direkt aufrufen. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) ruft es als Teil des Arbeitsbereichs Initialisierungsprozess.

##  <a name="movetooldown"></a>  CUserToolsManager::MoveToolDown

Verschiebt Sie in der Liste der Tools für das angegebene Benutzer-Tool nach unten.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Parameter

*pTool*<br/>
[in] Gibt das benutzertool "zu verschieben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das benutzertool erfolgreich, nach unten verschoben wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Methode schlägt fehl, wenn das Tool, das *pTool* gibt an, befindet sich nicht in der internen Liste oder wenn das Tool in der Liste letzte.

##  <a name="movetoolup"></a>  CUserToolsManager::MoveToolUp

Verschiebt Sie in der Liste der Tools für das angegebene Benutzer-Tool nach oben.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Parameter

*pTool*<br/>
[in] Gibt das benutzertool "zu verschieben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das benutzertool sich erfolgreich verschoben wurde, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Methode schlägt fehl, wenn das Tool, das *pTool* befindet sich nicht in der internen Liste angegeben wird oder wenn das Tool das erste Tool-Element in der Liste.

##  <a name="removetool"></a>  CUserToolsManager::RemoveTool

Entfernt das Tool für die angegebenen Benutzer aus der Anwendung an.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Parameter

*pTool*<br/>
[in, out] Ein Zeiger auf ein Tool, das entfernt werden.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Tool erfolgreich entfernt wurde. Andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn das Tool erfolgreich entfernt wurde, wird diese Methode löscht *pTool*.

##  <a name="savestate"></a>  CUserToolsManager::SaveState

Speichert Informationen über Benutzertools in der Windows-Registrierung.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Ein Pfad zu den Windows-Registrierungsschlüssel.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Zustand erfolgreich gespeichert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Methode speichert den aktuellen Zustand von der `CUserToolsManager` Objekt in der Windows-Registrierung.

In der Regel ist, Sie müssen nicht direkt aufrufen, diese Methode [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) ruft er automatisch als Teil des Serialisierungsprozesses "Arbeitsbereich" der Anwendung.

##  <a name="setdefext"></a>  CUserToolsManager::SetDefExt

Gibt an, die standarderweiterung, die die **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet in der **Befehl** Feld der **Tools** Registerkarte von der **anpassen** Dialogfeld.

```
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Parameter

*strDefExt*<br/>
[in] Eine Textzeichenfolge, die die Standard-Dateinamenerweiterung enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um eine Standard-Dateinamenerweiterung im Angeben der **Datei öffnen** Dialogfeld wird angezeigt, wenn der Benutzer eine Anwendung mit dem benutzertool zuordnen auswählt. Der Standardwert ist "Exe".

##  <a name="setfilter"></a>  CUserToolsManager::SetFilter

Gibt an, die Datei filtern, die die **Datei öffnen** Dialogfeld ( [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)) verwendet die **Befehl** Feld der **Tools** auf der Registerkarte der **Anpassen** Dialogfeld.

```
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Parameter

*strFilter*<br/>
[in] Gibt den Filter.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool-Klasse](../../mfc/reference/cusertool-class.md)
