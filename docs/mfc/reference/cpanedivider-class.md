---
title: Cpanedivider-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: d4888fbf2a95652b0a38adc8ecd059a7515636cb
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866118"
---
# <a name="cpanedivider-class"></a>Cpanedivider-Klasse

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

Die `CPaneDivider` -Klasse dividiert zwei Bereiche, dividiert zwei Gruppen von Bereichen oder trennt eine Gruppe von Bereichen vom Client Bereich des Hauptrahmen Fensters.

## <a name="syntax"></a>Syntax

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPaneDivider::CPaneDivider](#cpanedivider)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||
|[CPaneDivider::AddPane](#addpane)||
|[CPaneDivider::AddRecentPane](#addrecentpane)||
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CPaneDivider::CheckVisibility](#checkvisibility)||
|[CPaneDivider::CreateEx](#createex)|(Überschreibt [cbasepane:: deateex](../../mfc/reference/cbasepane-class.md#createex).)|
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Überschreibt [cbasepane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider::GetFirstPane](#getfirstpane)||
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider::GetWidth](#getwidth)||
|[CPaneDivider::Init](#init)||
|[CPaneDivider::InsertPane](#insertpane)||
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(Überschreibt [cbasepane:: isautohidemode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|
|[CPaneDivider::IsDefault](#isdefault)||
|[CPaneDivider::IsHorizontal](#ishorizontal)|(Überschreibt [cbasepane:: IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|
|[CPaneDivider::Move](#move)||
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||
|[CPaneDivider::OnShowPane](#onshowpane)||
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider::RemovePane](#removepane)||
|[CPaneDivider::ReplacePane](#replacepane)||
|[CPaneDivider::RepositionPanes](#repositionpanes)||
|[CPaneDivider::Serialize](#serialize)|(Überschreibt `CBasePane::Serialize`.)|
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||
|[CPaneDivider::ShowWindow](#showwindow)||
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPaneDivider::GetPanes](#getpanes)|Gibt die Liste der Bereiche zurück, die sich in der [cpanecontainer-Klasse](../../mfc/reference/cpanecontainer-class.md)befinden. Diese Methode sollte nur für Standard Bereichs Teiler aufgerufen werden.|
|[CPaneDivider::GetPaneDividers](#getpanedividers)|Gibt die Liste der Bereichs Teiler zurück, die sich in der [cpanecontainer-Klasse](../../mfc/reference/cpanecontainer-class.md)befinden. Diese Methode sollte nur für Standard Bereichs Teiler aufgerufen werden.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|Gibt die Standardbreite für alle Bereichs Teiler in der Anwendung in Pixel an.|
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|Enthält einen Zeiger auf die Lauf Zeit Klassen Informationen über `CPaneDivider`ein von abgeleitetes Objekt.|

## <a name="remarks"></a>Hinweise

Das Framework erstellt `CPaneDivider` Objekte automatisch, wenn ein Bereich angedockt ist.

Es gibt zwei Arten von Bereichs Teiler:

- ein Standard Bereichs Teiler wird erstellt, wenn eine Gruppe von Bereichen an eine Seite des Hauptrahmen Fensters angedockt wird. Der Standard Bereichs Teiler enthält einen Zeiger auf die [cpanecontainermanager-Klasse](../../mfc/reference/cpanecontainermanager-class.md) und leitet die meisten Vorgänge in der Gruppe von Bereichen (z. b. Ändern der Größe eines Bereichs oder Andocken eines anderen Bereichs oder Containers) an den Container-Manager um. Jeder Docking Bereich behält einen Zeiger auf seinen Standard Bereichs Teiler bei.

- Ein regulärer Bereichs Teiler dividiert nur zwei Bereiche in einem Container. Weitere Informationen finden Sie unter [cpanecontainer-Klasse](../../mfc/reference/cpanecontainer-class.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt den Abruf eines `CPaneDivider`-Objekts aus einem `CWorkspaceBar`-Objekt. Dieser Code Ausschnitt ist Teil des Beispiel für die [MDI-Registerkarten-Demo](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cpanedivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxPaneDivider.h

##  <a name="setautohidemode"></a>Cpanedivider:: abtaudehidemode

```
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>Parameter

in *bmode*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpanecontainermanager"></a>Cpanedivider:: setpanecontainermanager

```
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>Parameter

[in] *p*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="addpane"></a>Cpanedivider:: addpane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="addpanecontainer"></a>Cpanedivider:: addpanecontainer

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parameter

in *barcontainermanager*<br/>
in *bouteredge*<br/>
in *ptargetbar*<br/>
in *dwalignment*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="addrecentpane"></a>Cpanedivider:: addrecentpane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="calcexpecteddockedrect"></a>Cpanedivider:: calcexpecteddockedrect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parameter

in *pwndper Dock*<br/>
in *ptmouse*<br/>
in *rectresult*<br/>
[in] *bDrawTab*<br/>
[in] *ppTargetBar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="calcfixedlayout"></a>Cpanedivider:: calcfixedlayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

in *bstretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="checkvisibility"></a>Cpanedivider:: checkvisibility

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="cpanedivider"></a>Cpanedivider:: cpanedivider

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parameter

in *bdefaultlider*<br/>
in *pparent*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="createex"></a>Cpanedivider:: up-Ex

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parameter

in *dwstyleex*<br/>
in *dwstyle*<br/>
in *Rect*<br/>
in *pparser*<br/>
[in] *nID*<br/>
in *pContext*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="doesallowdyninsertbefore"></a>Cpanedivider::D oesallowdyninsertbefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="doescontainfloatingpane"></a>Cpanedivider::D oescontainfloatingpane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="findpanecontainer"></a>Cpanedivider:: findpanecontainer

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>
[in] *bLeftBar*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="findtabbedpane"></a>Cpanedivider:: findtabbedpane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>Parameter

[in] *nID*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getdefaultwidth"></a>Cpanedivider:: getdefaultwidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getfirstpane"></a>Cpanedivider:: getfirstpane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanedividers"></a>Cpanedivider:: getpanedividers

Gibt die Liste der Bereichs Teiler zurück, die sich in der [cpanecontainer-Klasse](../../mfc/reference/cpanecontainer-class.md)befinden. Diese Methode sollte nur für Standard Bereichs Teiler aufgerufen werden.

```
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>Parameter

*lstSliders*<br/>
vorgenommen Enthält die Liste der Bereichs Teiler, die sich im Bereichs Container befinden.

### <a name="remarks"></a>Hinweise

Diese Methode sollte nur für Standard Bereichs Teiler aufgerufen werden. Ein Standard Bereichs Teiler ist ein unter Teiler, der die Größe des gesamten Bereichs Containers ändert.

##  <a name="getpanedividerstyle"></a>Cpanedivider:: getpanedividerstyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanes"></a>Cpanedivider:: getpanels

Gibt die Liste der Bereiche zurück, die sich in der [cpanecontainer-Klasse](../../mfc/reference/cpanecontainer-class.md)befinden. Diese Methode sollte nur aufgerufen werden, um Standard Bereichs Teiler abzurufen.

```
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>Parameter

*lstBars*<br/>
vorgenommen Enthält die Liste der Bereiche, die sich im Bereichs Container befinden.

### <a name="remarks"></a>Hinweise

Diese Methode sollte nur für Standard Bereichs Teiler aufgerufen werden. Ein Standard Bereichs Teiler ist ein unter Teiler, der die Größe des gesamten Bereichs Containers ändert.

##  <a name="getrootcontainerrect"></a>Cpanedivider:: getrootcontainerrect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getwidth"></a>Cpanedivider:: getWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="init"></a>Cpanedivider:: init

```
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parameter

in *bdefaultlider*<br/>
in *pparent*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="insertpane"></a>Cpanedivider:: insertpane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

in *pbartoinsert*<br/>
in *ptargetbar*<br/>
in *dwalignment*<br/>
in *lprect*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isautohidemode"></a>Cpanedivider:: isautohidemode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isdefault"></a>Cpanedivider:: IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ishorizontal"></a>Cpanedivider:: IsHorizontal

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="m_ndefaultwidth"></a>Cpanedivider:: m_nDefaultWidth

Gibt die Standardbreite aller Bereichs Teiler in der Anwendung in Pixel an.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

##  <a name="move"></a>Cpanedivider:: Move

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parameter

[in] *ptOffset*<br/>
in *banpassungen-Layout*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="m_psliderrtc"></a>Cpanedivider:: m_pSliderRTC

Enthält einen Zeiger auf Lauf Zeit Klassen Informationen über `CPaneDivider`ein von abgeleitetes Objekt.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>Hinweise

Legen Sie diese Member-Variable fest, wenn Sie einen benutzerdefinierten Bereichs Teiler erstellen. Dies ermöglicht es dem Framework, den Bereichs Teiler zu erstellen, wenn der Bereich gezeichnet wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die `m_pSliderRTC` -Element Variable festgelegt wird:

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

##  <a name="notifyaboutrelease"></a>Cpanedivider:: notifyabamplease

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>Hinweise

##  <a name="onshowpane"></a>Cpanedivider:: onshowpane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>
[in] *bShow*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="releaseemptypanecontainers"></a>Cpanedivider:: releaseemptypanecontainers

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>Hinweise

##  <a name="removepane"></a>Cpanedivider:: removepane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="replacepane"></a>Cpanedivider:: replacepane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>Parameter

in *pbartoreplace*<br/>
in *pbartoreplacewith*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="repositionpanes"></a>Cpanedivider:: repositionbereichs

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parameter

in *neu (neu* )<br/>
in *hdwp*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="serialize"></a>Cpanedivider:: Serialize

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

[in] *ar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="showwindow"></a>Cpanedivider:: ShowWindow

```
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parameter

in *nCmdShow*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="storerecentdocksiteinfo"></a>Cpanedivider:: storerecentdocksiteinfo

```
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="storerecenttabrelatedinfo"></a>Cpanedivider:: storerecenttabrelatedinfo

```
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>Parameter

in *pdockingbar*<br/>
[in] *pTabbedBar*<br/>

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPaneContainerManager-Klasse](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer-Klasse](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager-Klasse](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)
