---
title: CMFCDropDownFrame-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 534dc90443371c8440e0cb317540f2cf80f6eacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237372"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame-Klasse

Enthält die Dropdown-Rahmens Fensterfunktionalität, Dropdown-Symbolleisten und Dropdown-Symbolleisten-Schaltflächen.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Standardkonstruktor|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCDropDownFrame::Create](#create)|Erstellt ein `CMFCDropDownFrame`-Objekt.|
|`CMFCDropDownFrame::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Ruft die übergeordnete Menüleiste des Dropdown-Rahmens ab.|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Ruft die übergeordnete im Popupmenü des Dropdown-Rahmens ab.|
|`CMFCDropDownFrame::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Automatisch neu positioniert und den Dropdown-Rahmen.|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Legt fest, ob das untergeordnete Dropdown-Symbolleisten-Fenster automatisch zerstört wird.|

### <a name="remarks"></a>Hinweise

Diese Klasse ist nicht vorgesehen, direkt aus Ihrem Code verwendet werden.

Das Framework verwendet diese Klasse auf Frame-Verhalten zum Bereitstellen der `CMFCDropDownToolbar` und `CMFCDropDownToolbarButton` Klassen. Weitere Informationen zu diesen Klassen finden Sie unter [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) und [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie einen Zeiger zum Abrufen einer `CMFCDropDownFrame` -Objekt aus einer `CFrameWnd` -Klasse, und wie das untergeordnete Element Dropdown-Symbolleisten-Fenster, um automatisch zerstört werden festgelegt.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdropdowntoolbar.h

##  <a name="create"></a>  CMFCDropDownFrame::Create

Erstellt ein `CMFCDropDownFrame`-Objekt.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pWndParent*|[in] Das übergeordnete Fenster des Dropdown-Rahmens.|
|*w*|[in] Die horizontale Bildschirmkoordinate für den Speicherort des Dropdown-Rahmens.|
|*y*|[in] Die vertikale Bildschirmkoordinate für den Speicherort des Dropdown-Rahmens.|
|*pWndOriginToolbar*|[in] Die Symbolleiste mit der Dropdown-Schaltflächen, die diese Methode verwendet, um das neue rahmenobjekt der Dropdown-aufzufüllen.|

### <a name="return-value"></a>Rückgabewert

True, wenn der Dropdown-Rahmen erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Basis [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) Methode zum Erstellen des Dropdown-Frame-Fensters im WS_POPUP-Format. Das Dropdown-Frame-Fenster wird angezeigt, an den angegebenen Bildschirmkoordinaten. Diese Methode schlägt fehl, wenn die [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) Methode gibt FALSE zurück.

Die `CMFCDropDownFrame` Klasse erstellt eine Kopie der bereitgestellten `CMFCDropDownToolBar` Parameter. Diese Methode kopiert die Schaltflächenbilder und der Schaltflächenstatus aus der `pWndOriginToolbar` Parameter, um die `m_pWndOriginToolbar` -Datenmember.

##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar

Ruft die übergeordnete Menüleiste des Dropdown-Rahmens ab.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die übergeordnete Menüleiste des Dropdown-Rahmens oder NULL, wenn der Frame kein übergeordnetes Element besitzt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Menüleiste "übergeordneten" Schaltfläche "übergeordneten" ab. Diese Methode gibt NULL zurück, wenn die Schaltfläche "übergeordneten" verfügt über keine übergeordnete-Menüleiste oder der Dropdown-Rahmen keine Schaltfläche "übergeordneten hat".

##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu

Ruft die übergeordnete im Popupmenü des Dropdown-Rahmens ab.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die übergeordnete Dropdown-Menü der Dropdown-Rahmens, oder NULL, wenn der Frame kein übergeordnetes Element besitzt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft im übergeordneten Menü ab, von der übergeordneten-Schaltfläche. Diese Methode gibt NULL zurück, wenn die Schaltfläche "übergeordneten" verfügt über keine übergeordneten Menüs oder der Dropdown-Rahmen keine Schaltfläche "übergeordneten hat".

##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout

Automatisch neu positioniert und den Dropdown-Rahmen.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*bNotify*|[in] Nicht verwendet.|

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn der Dropdown-Rahmen erstellt wird oder das übergeordnete Fenster angepasst wird. Diese Methode berechnet die Position und Größe des Dropdown-Rahmens mit die Position und Größe des übergeordneten Fensters.

##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy

Legt fest, ob das untergeordnete Dropdown-Symbolleisten-Fenster automatisch zerstört wird.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*bAutoDestroy*<br/>
[in] True, um das zugeordnete Dropdown-Symbolleisten-Fenster automatisch zu löschen. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn *bAutoDestroy* ist "true", und klicken Sie dann die `CMFCDropDownFrame` Destruktor zerstört den zugeordneten Dropdown-Symbolleisten-Fenster. Der Standardwert ist "true".

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
