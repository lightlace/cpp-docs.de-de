---
title: CMFCDropDownToolBar-Klasse
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: f2c4135d2a27928dbde4299fa1f8eda42237d893
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776790"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar-Klasse

Eine Symbolleiste, die angezeigt wird, wenn der Benutzer eine Symbolleisten-Schaltfläche der obersten Ebene drückt und gedrückt hält.

   Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.
## <a name="syntax"></a>Syntax

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Überschreibt `CPane::AllowShowOnPaneMenu`.)|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(Überschreibt [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(Überschreibt [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(Überschreibt `CMFCToolBar::OnSendCommand`.)|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CMFCToolBar::OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>Hinweise

Ein `CMFCDropDownToolBar` -Objekt kombiniert die visuelle Darstellung des eine Symbolleiste mit dem Verhalten eines Popup-Menüs. Wenn ein Benutzer drückt und gedrückt hält eine Dropdown-Symbolleisten-Schaltfläche (finden Sie unter [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), wird eine Dropdown-Symbolleiste angezeigt, und der Benutzer kann aus der Dropdown-Symbolleiste eine Schaltfläche auswählen, indem Sie einen Bildlauf dorthin durchführen und Freigeben der Maus Schaltfläche ". Nachdem der Benutzer eine Schaltfläche in der Dropdown-Symbolleiste ausgewählt hat, wird diese Schaltfläche als die aktuelle Schaltfläche auf der Symbolleiste der obersten Ebene angezeigt.

Ein Dropdown-Symbolleisten kann nicht angepasst oder angedockt werden kann, und er verfügt nicht über einem abtrennbaren Zustand.

Die folgende Abbildung zeigt eine `CMFCDropDownToolBar` Objekt:

![Beispiel für cmfcdropdowntoolbar](../../mfc/reference/media/cmfcdropdown.png "Beispiel für cmfcdropdowntoolbar")

Sie erstellen eine `CMFCDropDownToolBar` Objekt die gleiche Weise, die Sie erstellen eine normale-Symbolleiste (finden Sie unter [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)).

So fügen Sie die Dropdown-Symbolleisten in einer übergeordneten Symbolleiste ein:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

2. Erstellen Sie eine `CMFCDropDownToolBarButton` -Objekt, das die Dropdown-Symbolleiste enthält ein (Weitere Informationen finden Sie unter [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).

3. Ersetzen Sie die Schaltfläche "dummy", mit der `CMFCDropDownToolBarButton` Objekt mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Weitere Informationen zu den Symbolleisten-Schaltflächen, finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Dropdown-Symbolleisten finden Sie das Beispielprojekt VisualStudioDemo.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der die `CMFCDropDownToolBar` Klasse. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdropdowntoolbar.h

##  <a name="allowshowonpanemenu"></a>  CMFCDropDownToolBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="loadbitmap"></a>  CMFCDropDownToolBar::LoadBitmap

Lädt Symbolleistenbilder aus Anwendungsressourcen.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>Parameter

*uiResID*<br/>
[in] Die Ressourcen-ID der Bitmap, die auf die aktiven Symbolleistenbilder verweist.

*uiColdResID*<br/>
[in] Die Ressourcen-ID der Bitmap, die auf die inaktiven Symbolleistenbilder verweist.

*uiMenuResID*<br/>
[in] Die Ressourcen-ID der Bitmap, die auf die normalen Menübilder verweist.

*bLocked*<br/>
[in] True, um die Symbolleiste zu sperren. andernfalls "false".

*uiDisabledResID*<br/>
[in] Die Ressourcen-ID der Bitmap, die auf die deaktivierten Symbolleistenbilder verweist.

*uiMenuDisabledResID*<br/>
[in] Die Ressourcen-ID der Bitmap, die auf die deaktivierten Menübilder verweist.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Die [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) -Methode ruft diese Methode auf, um die Bilder zu laden, die der Symbolleiste zugeordnet sind. Setzen Sie diese Methode außer Kraft, um die Bildressourcen benutzerdefiniert zu laden.

Rufen Sie die `LoadBitmapEx` -Methode auf, um nach der Erstellung der Symbolleiste weitere Bilder zu laden.

##  <a name="loadtoolbar"></a>  CMFCDropDownToolBar::LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>Parameter

[in] *uiResID*<br/>

[in] *UiColdResID*<br/>

[in] *UiMenuResID*<br/>

[in] *"Bool"*<br/>

[in] *uiDisabledResID*<br/>

[in] *uiMenuDisabledResID*<br/>

[in] *uiHotResID*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parameter

[in] *nFlags*<br/>

[in] *point*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parameter

[in] *nFlags*<br/>

[in] *point*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pButton*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parameter

[in] *pTarget*<br/>

[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
