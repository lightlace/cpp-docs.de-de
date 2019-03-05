---
title: CMFCVisualManagerVS2005-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
ms.openlocfilehash: 212ef69350fbc85e6e0cc76bd505b2a895e75c8e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279964"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005-Klasse

`CMFCVisualManagerVS2005` Ermöglicht es einer Anwendung eine Microsoft Visual Studio 2005-Darstellung.

## <a name="syntax"></a>Syntax

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](#getdockingtabsborderssize)|Das Framework ruft diese Methode auf, wenn es sich um einen Bereich zeichnet, der im Registerkartenformat und angedockt ist. (Überschreibt [CMFCVisualManager::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](#getmditabsborderssize)|Das Framework ruft diese Methode, um die Rahmenstärke eines Fensters MDITabs zu ermitteln, bevor sie das Fenster zeichnet. (Überschreibt [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize).)|
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|(Überschreibt [CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor).)|
|[CMFCVisualManagerVS2005::GetTabFrameColors](#gettabframecolors)|(Überschreibt [CMFCVisualManagerOffice2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors).)|
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|Gibt zurück, ob der automatisch ausblendbaren Schaltflächen in der aktuellen visuellen Manager überlappen. (Überschreibt [CMFCVisualManager::HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons).)|
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|(Überschreibt [CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder).)|
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](#ondrawcaptionbutton)|(Überschreibt `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.)|
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](#ondrawpanecaption)|(Überschreibt [CMFCVisualManagerOffice2003::OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption).)|
|[CMFCVisualManagerVS2005::OnDrawSeparator](#ondrawseparator)|(Überschreibt [CMFCVisualManagerOffice2003::OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator).)|
|[CMFCVisualManagerVS2005::OnDrawTab](#ondrawtab)|(Überschreibt [CMFCVisualManagerOffice2003::OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab).)|
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](#ondrawtoolboxframe)|(Überschreibt [CMFCVisualManager::OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe).)|
|[CMFCVisualManagerVS2005::OnEraseTabsArea](#onerasetabsarea)|(Überschreibt [CMFCVisualManagerOffice2003::OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea).)|
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|(Überschreibt [CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground).)|
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](#onfillhighlightedarea)|(Überschreibt [CMFCVisualManagerOffice2003::OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](#onfillminiframecaption)|(Überschreibt `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.)|
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](#onupdatesystemcolors)|(Überschreibt [CMFCVisualManagerOffice2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors).)|

## <a name="remarks"></a>Hinweise

Sie verwenden die CMFCVisualManagerVS2005-Klasse so ändern Sie die visuelle Darstellung Ihrer Anwendung, die von der Microsoft Visual Studio 2005 ähneln.

Alle Member dieser Klasse sind virtuelle Funktionen, die von den Vorgänger dieser Klasse abgeleitet sind [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie mit den visuellen Manager VS 2005. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxvisualmanagervs2005.h

##  <a name="getdockingtabsborderssize"></a>  CMFCVisualManagerVS2005::GetDockingTabsBordersSize

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getmditabsborderssize"></a>  CMFCVisualManagerVS2005::GetMDITabsBordersSize

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpropertygridgroupcolor"></a>  CMFCVisualManagerVS2005::GetPropertyGridGroupColor

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>Parameter

[in] *pPropList*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="gettabframecolors"></a>  CMFCVisualManagerVS2005::GetTabFrameColors

```
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,
    COLORREF& clrDark,
    COLORREF& clrBlack,
    COLORREF& clrHighlight,
    COLORREF& clrFace,
    COLORREF& clrDarkShadow,
    COLORREF& clrLight,
    CBrush*& pbrFace,
    CBrush*& pbrBlack);
```

### <a name="parameters"></a>Parameter

[in] *pTabWnd*<br/>
[in] *clrDark*<br/>
[in] *clrBlack*<br/>
[in] *clrHighlight*<br/>
[in] *clrFace*<br/>
[in] *clrDarkShadow*<br/>
[in] *clrLight*<br/>
[in] *pbrFace*<br/>
[in] *pbrBlack*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="hasoverlappedautohidebuttons"></a>  CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ondrawautohidebuttonborder"></a>  CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *RectBounds*<br/>
[in] *rectBorderSize*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="ondrawcaptionbutton"></a>  CMFCVisualManagerVS2005::OnDrawCaptionButton

```
virtual void OnDrawCaptionButton(
    CDC* pDC,
    CMFCCaptionButton* pButton,
    BOOL bActive,
    BOOL bHorz,
    BOOL bMaximized,
    BOOL bDisabled,
    int nImageID = -1);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *pButton*<br/>
[in] *bActive*<br/>
[in] *bHorz*<br/>
[in] *bMaximized*<br/>
[in] *bDeaktiviert*<br/>
[in] *nImageID*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="ondrawpanecaption"></a>  CMFCVisualManagerVS2005::OnDrawPaneCaption

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *pBar*<br/>
[in] *bActive*<br/>
[in] *rectCaption*<br/>
[in] *RectButtons*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ondrawseparator"></a>  CMFCVisualManagerVS2005::OnDrawSeparator

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *pBar*<br/>
[in] *rect*<br/>
[in] *bIsHoriz*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="ondrawtab"></a>  CMFCVisualManagerVS2005::OnDrawTab

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rectTab*<br/>
[in] *iTab*<br/>
[in] *bIsActive*<br/>
[in] *pTabWnd*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="ondrawtoolboxframe"></a>  CMFCVisualManagerVS2005::OnDrawToolBoxFrame

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rect*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onerasetabsarea"></a>  CMFCVisualManagerVS2005::OnEraseTabsArea

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rect*<br/>
[in] *pTabWnd*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onfillautohidebuttonbackground"></a>  CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rect*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onfillhighlightedarea"></a>  CMFCVisualManagerVS2005::OnFillHighlightedArea

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rect*<br/>
[in] *pBrush*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onfillminiframecaption"></a>  CMFCVisualManagerVS2005::OnFillMiniFrameCaption

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>
[in] *rectCaption*<br/>
[in] *pFrameWnd*<br/>
[in] *bActive*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onupdatesystemcolors"></a>  CMFCVisualManagerVS2005::OnUpdateSystemColors

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerOfficeXP-Klasse](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[CMFCVisualManagerWindows-Klasse](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[CMFCVisualManagerOffice2003-Klasse](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
