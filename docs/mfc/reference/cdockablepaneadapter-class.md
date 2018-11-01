---
title: CDockablePaneAdapter-Klasse
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
ms.openlocfilehash: 6088d7ed9f4d8f54bfe5ea7f7b77cdabfd11768f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522953"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter-Klasse

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

Das Framework instanziiert in der Regel Objekte dieser Klasse, bei der Verwendung der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) oder [cmfcbasetabctrl:: insertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) Methoden.

Wenn Sie anpassen möchten die `CDockablePaneAdapter` Verhalten einfach eine neue Klasse davon ableiten und die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, mithilfe von [cmfcbasetabctrl:: Setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

Gibt das zugrunde liegende Fenster für die Karte des andockbaren Bereich zurück.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das umschlossene Fenster.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um das umschlossene Fenster zuzugreifen.

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

Lädt den Zustand des Bereichs aus der Registrierung.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Der Profilname.

*nIndex*<br/>
[in] Der Index des Profils.

*uiID*<br/>
[in] Der Bereich-ID

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

Speichert den Zustand des Bereichs in der Registrierung.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Der Profilname.

*nIndex*<br/>
[in] Der Profil-Index (standardmäßig die Steuerelement-ID des Fensters).

*uiID*<br/>
[in] Der Bereich-ID

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

Das zugrunde liegende Fenster festgelegt für die Karte des andockbaren Bereich.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Ein Zeiger auf das Fenster für den Bereich-Adapter zum umschließen.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
