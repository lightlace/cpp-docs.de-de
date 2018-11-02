---
title: CMFCBaseToolBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
ms.openlocfilehash: 84756eb177fcec1981f3f2ed018d57eb27df9823
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523701"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar-Klasse

Die Basisklasse für Symbolleisten.

## <a name="syntax"></a>Syntax

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|Standardkonstruktor|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Gibt den Andockmodus zurück. (Überschreibt [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|
|[CMFCBaseToolBar::GetMinSize](#getminsize)|Gibt die minimale Größe einer Symbolleiste zurück. (Überschreibt [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|Wird vom Framework aufgerufen, nach im Bereich der übergeordneten Änderungen. (Überschreibt [CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxbasetoolbar.h

##  <a name="getdockingmode"></a>  CMFCBaseToolBar::GetDockingMode

Gibt den Andockmodus zurück.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Rückgabewert

Der Andockmodus.

##  <a name="getminsize"></a>  CMFCBaseToolBar::GetMinSize

Gibt die minimale Größe einer Symbolleiste zurück.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parameter

*size*<br/>
[out] Die minimale Größe einer Symbolleiste.

##  <a name="onafterchangeparent"></a>  CMFCBaseToolBar::OnAfterChangeParent

Wird vom Framework aufgerufen, nach im Bereich der übergeordneten Änderungen.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parameter

*pWndOldParent*<br/>
[in] Ein Zeiger auf das vorherige übergeordnete Fenster.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
