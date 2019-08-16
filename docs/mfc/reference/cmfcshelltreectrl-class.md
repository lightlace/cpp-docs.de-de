---
title: Cmfcshelltreectrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: 97136342049a54d45af893962025f01eda4366d4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504909"
---
# <a name="cmfcshelltreectrl-class"></a>Cmfcshelltreectrl-Klasse

Die `CMFCShellTreeCtrl` -Klasse erweitert die Funktionen der [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md) , indem eine Hierarchie von shellelementen angezeigt wird.

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.
## <a name="syntax"></a>Syntax

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Gibt eine Kombination von Flags zurück, die an [IShellFolder:: enumubjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)übermittelt werden.|
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Ruft den Pfad zu einem Element ab.|
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Gibt einen Zeiger auf das [cmfcshelllistctrl-Klassen](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt zurück, das mit diesem `CMFCShellTreeCtrl` -Objekt zum Erstellen eines Explorer-ähnlichen Fensters verwendet wird.|
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Diese Member-Funktion wird durch das übergeordnete Fenster dieses Fensters aufgerufen, wenn eine Benachrichtigungs Meldung empfangen wird, die für dieses Fenster gilt. (Überschreibt [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl::Refresh](#refresh)|Aktualisiert das aktuelle `CMFCShellTreeCtrl` -Objekt und zeichnet es neu.|
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Wählt das entsprechende Struktur Steuerungselement auf Grundlage eines angegebenen PIDL-oder Zeichen folgen Pfads aus.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Legt Flags fest, um den Struktur Kontext zu filtern (ähnlich den von `IShellFolder::EnumObjects`verwendeten Flags).|
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Legt eine Beziehung zwischen dem aktuellen `CMFCShellTreeCtrl` -Objekt und `CMFCShellListCtrl` einem-Objekt fest.|

## <a name="remarks"></a>Hinweise

Diese Klasse erweitert die `CTreeCtrl` -Klasse, indem das Programm das Einschließen von Windows-shellelementen in die Struktur ermöglicht. Diese Klasse kann einem `CMFCShellListCtrl` -Objekt zugeordnet werden, um ein umfassendes Explorer-Fenster zu erstellen. Wenn Sie ein Element in der Struktur auswählen, wird eine Liste der Windows-shellelemente in der zugeordneten Liste angezeigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxshelltreectrl. h

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CMFCShellTreeCtrl`-Klasse erstellt wird. Dieser Code Ausschnitt ist Teil des [Explorer](../../overview/visual-cpp-samples.md)-Beispiels.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>Cmfcshelltreectrl:: enableshellcontextmenu

Aktiviert das Kontextmenü.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in Ein boolescher Wert, der angibt, ob das Kontextmenü aktiviert werden soll.

##  <a name="getflags"></a>Cmfcshelltreectrl:: GetFlags

Gibt die Flags zurück, die für das [cmfcshelltreectrl-Klassen](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt festgelegt wurden.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Rückgabewert

Ein DWORD-Wert, der die Kombination der zurzeit festgelegten Flags angibt.

### <a name="remarks"></a>Hinweise

Die im `CMFCShellTreeCtrl` festgelegten Flags werden an die [IShellFolder:: enumubjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) -Methode gesendet, wenn das Objekt aktualisiert wird. Sie können die Flags mit der [cmfcshelltreectrl:: setFlags](#setflags) -Methode ändern.

##  <a name="getitempath"></a>Cmfcshelltreectrl:: getitempath

Ruft den Pfad eines Elements im [cmfcshelltreectrl-Klassen](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt ab.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Parameter

*strPath*<br/>
vorgenommen Ein Verweis auf einen Zeichen folgen Parameter. Die-Methode schreibt den Pfad des Elements in diesen Parameter.

*htreeItem*<br/>
in Die-Methode ruft den Pfad für dieses Struktur Steuerelement ab.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn diese Methode fehlschlägt , enthält "strepath" die leere Zeichenfolge.

Wenn Sie *HTREEITEM*nicht angeben, versucht diese Methode, die Zeichenfolge für das aktuell ausgewählte Element abzurufen. Wenn kein Element ausgewählt ist und *HTREEITEM* den Wert NULL hat, schlägt diese Methode fehl.

##  <a name="getrelatedlist"></a>Cmfcshelltreectrl:: getrelatedlist

Gibt einen Zeiger auf das [cmfcshelllistctrl-Klassen](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt zurück, das mit diesem [cmfcshelltreectrl](../../mfc/reference/cmfcshelltreectrl-class.md) -Objekt verknüpft ist.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `CMFCShellListCtrl` -Objekt, das mit diesem Struktur Steuerelement-Objekt verknüpft ist.

### <a name="remarks"></a>Hinweise

Mithilfe eines `CMFCShellListCtrl` -Objekts und eines `CMFCShellTreeCtrl` -Objekts können Sie ein Explorer-ähnliches Fenster erstellen. Verwenden Sie die-Methode [cmfcshelltreectrl:: settrelatedlist](#setrelatedlist) , um die beiden Klassen zuzuordnen. Nachdem Sie zugeordnet wurden, aktualisiert das Framework automatisch den `CMFCShellListCtrl` , wenn sich die Auswahl `CMFCShellTreeCtrl` in der ändert.

##  <a name="onchildnotify"></a>Cmfcshelltreectrl:: OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Parameter

in *Nachricht*<br/>
in *wParam*<br/>
[in] *lParam*<br/>
in *plresult*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ongetitemicon"></a>Cmfcshelltreectrl:: ongetitemicon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

in *pitem*<br/>
in *bausgewählt*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ongetitemtext"></a>Cmfcshelltreectrl:: ongetitemtext

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parameter

in *pitem*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="refresh"></a>Cmfcshelltreectrl:: Refresh

Aktualisiert das [cmfcshelltreectrl](../../mfc/reference/cmfcshelltreectrl-class.md)-und zeichnet es neu.

```
void Refresh();
```

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie die Hierarchie der in `CMFCShellTreeCtrl`angezeigten Elemente aktualisieren.

##  <a name="selectpath"></a>Cmfcshelltreectrl:: selectpath

Wählt ein Element in der [cmfcshelltreectrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) auf Grundlage des angegebenen Pfads aus.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Parameter

*lpszPath*<br/>
in Eine Zeichenfolge, die den Pfad eines Elements angibt.

*lpidl*<br/>
in Eine PIDL, die das Element angibt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; E_FAIL andernfalls.

##  <a name="setflags"></a>Cmfcshelltreectrl:: setFlags

Legt Flags fest, um den Struktur Kontext zu filtern.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
in Die festzulegenden Flags.

*bRefresh*<br/>
in Ein boolescher Wert, der `CMFCShellTreeCtrl` angibt, ob sofort aktualisiert werden soll.

### <a name="remarks"></a>Hinweise

Übergibt alle festgelegten Flags an [IShellFolder:: enumubjects.](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) `CMFCShellTreeCtrl` Weitere Informationen zu den Werten verschiedener Flags finden Sie unter [IShellFolder:: enumubjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

##  <a name="setrelatedlist"></a>Cmfcshelltreectrl:: settrelatedlist

Ordnet ein [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt einem [cmfcshelltreectrl](../../mfc/reference/cmfcshelltreectrl-class.md) -Objekt zu.

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Parameter

*pShellList*<br/>
in Ein Zeiger auf ein `CMFCShellListCtrl` -Objekt.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird `CMFCShellListCtrl` eine einem zugeordnet. `CMFCShellTreeCtrl` Diese Objekte werden möglicherweise als Explorer-Fenster angezeigt: Wenn der Benutzer ein Objekt in der `CMFCShellTreeCtrl`auswählt, werden die zugehörigen Elemente `CMFCShellListCtrl` in automatisch aktualisiert.

Verwenden Sie die [cmfcshelltreectrl:: getrelatedlist](#getrelatedlist) -Methode, `CMFCShellListCtrl` um den zugeordneten `CMFCShellTreeCtrl`abzurufen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md)
