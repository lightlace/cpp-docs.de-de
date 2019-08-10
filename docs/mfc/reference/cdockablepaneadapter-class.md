---
title: Cdockablepaneadapter-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 88c125c63f9dbfe272f5d543e996366575fc533b
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866225"
---
# <a name="cdockablepaneadapter-class"></a>Cdockablepaneadapter-Klasse

Bietet Andockunterstützung für von `CWnd`abgeleitete Bereiche.

## <a name="syntax"></a>Syntax

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Gibt das umschlossene Fenster zurück.|
|[CDockablePaneAdapter::LoadState](#loadstate)|(Überschreibt [CDockablePane:: LoadState](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|(Überschreibt [CDockablePane:: SaveState](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Hinweise

Normalerweise instanziiert das Framework Objekte dieser Klasse, wenn Sie die [cmfcbasetabctrl:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) -Methode oder die [cmfcbasetabctrl:: InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) -Methode verwenden.

Wenn Sie das `CDockablePaneAdapter` Verhalten anpassen möchten, leiten Sie einfach eine neue Klasse davon ab, und legen Sie die Lauf Zeit Klassen Informationen mithilfe von [cmfcbasetabctrl:: setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)auf ein Fenster im Registerkarten Format fest.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPANE](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockablePane](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cdockablepaneadapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdockablepaneadapter. h

##  <a name="getwrappedwnd"></a>Cdockablepaneadapter:: getwrappeer dwnd

Gibt das zugrunde liegende Fenster für den Adapter des andockbaren Bereichs zurück.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das umschließende Fenster.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um auf das umschließende Fenster zuzugreifen.

##  <a name="loadstate"></a>Cdockablepaneadapter:: LoadState

Lädt den Zustand des Bereichs aus der Registrierung.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
in Der Profilname.

*nIndex*<br/>
in Der Profil Index.

*uiID*<br/>
in Die Bereichs-ID.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="savestate"></a>Cdockablepaneadapter:: SaveState

Speichert den Zustand des Bereichs in der Registrierung.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
in Der Profilname.

*nIndex*<br/>
in Der Profil Index (standardmäßig die Steuerelement-ID des Fensters).

*uiID*<br/>
in Die Bereichs-ID.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setwrappedwnd"></a>Cdockablepaneadapter:: setwrappeer dwnd

Legt das zugrunde liegende Fenster für den Adapter des andockbaren Bereichs fest.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Ein Zeiger auf das Fenster, in dem der Bereichs Adapter umschlossen werden soll.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
