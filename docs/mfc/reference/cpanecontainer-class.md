---
title: Klasse CPaneContainer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneContainer
- AFXPANECONTAINER/CPaneContainer
- AFXPANECONTAINER/CPaneContainer::CPaneContainer
- AFXPANECONTAINER/CPaneContainer::AddPane
- AFXPANECONTAINER/CPaneContainer::AddRef
- AFXPANECONTAINER/CPaneContainer::AddSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::CalcAvailablePaneSpace
- AFXPANECONTAINER/CPaneContainer::CalcAvailableSpace
- AFXPANECONTAINER/CPaneContainer::CalculateRecentSize
- AFXPANECONTAINER/CPaneContainer::CheckPaneDividerVisibility
- AFXPANECONTAINER/CPaneContainer::Copy
- AFXPANECONTAINER/CPaneContainer::DeletePane
- AFXPANECONTAINER/CPaneContainer::FindSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::FindTabbedPane
- AFXPANECONTAINER/CPaneContainer::GetAssociatedSiblingPaneIDs
- AFXPANECONTAINER/CPaneContainer::GetLeftPane
- AFXPANECONTAINER/CPaneContainer::GetLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetMinSize
- AFXPANECONTAINER/CPaneContainer::GetMinSizeLeft
- AFXPANECONTAINER/CPaneContainer::GetMinSizeRight
- AFXPANECONTAINER/CPaneContainer::GetNodeCount
- AFXPANECONTAINER/CPaneContainer::GetPaneDivider
- AFXPANECONTAINER/CPaneContainer::GetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerRect
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerStyle
- AFXPANECONTAINER/CPaneContainer::GetRecentPercent
- AFXPANECONTAINER/CPaneContainer::GetRefCount
- AFXPANECONTAINER/CPaneContainer::GetResizeStep
- AFXPANECONTAINER/CPaneContainer::GetRightPane
- AFXPANECONTAINER/CPaneContainer::GetRightPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetTotalReferenceCount
- AFXPANECONTAINER/CPaneContainer::GetWindowRect
- AFXPANECONTAINER/CPaneContainer::IsDisposed
- AFXPANECONTAINER/CPaneContainer::IsEmpty
- AFXPANECONTAINER/CPaneContainer::IsLeftPane
- AFXPANECONTAINER/CPaneContainer::IsLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::IsLeftPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsRightPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsVisible
- AFXPANECONTAINER/CPaneContainer::Move
- AFXPANECONTAINER/CPaneContainer::OnDeleteHidePane
- AFXPANECONTAINER/CPaneContainer::OnMoveInternalPaneDivider
- AFXPANECONTAINER/CPaneContainer::OnShowPane
- AFXPANECONTAINER/CPaneContainer::Release
- AFXPANECONTAINER/CPaneContainer::ReleaseEmptyPaneContainer
- AFXPANECONTAINER/CPaneContainer::RemoveNonValidPanes
- AFXPANECONTAINER/CPaneContainer::RemovePane
- AFXPANECONTAINER/CPaneContainer::Resize
- AFXPANECONTAINER/CPaneContainer::ResizePane
- AFXPANECONTAINER/CPaneContainer::ResizePartOfPaneContainer
- AFXPANECONTAINER/CPaneContainer::Serialize
- AFXPANECONTAINER/CPaneContainer::SetPane
- AFXPANECONTAINER/CPaneContainer::SetPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetPaneDivider
- AFXPANECONTAINER/CPaneContainer::SetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetRecentPercent
- AFXPANECONTAINER/CPaneContainer::SetUpByID
- AFXPANECONTAINER/CPaneContainer::StoreRecentDockSiteInfo
- AFXPANECONTAINER/CPaneContainer::StretchPaneContainer
dev_langs:
- C++
helpviewer_keywords:
- CPaneContainer class
ms.assetid: beb79e08-f611-4d66-ba04-053baa79bf86
caps.latest.revision: 32
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c6db2e98d9c9301559d8a689cc4094a5a423aa7f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cpanecontainer-class"></a>CPaneContainer-Klasse
Die `CPaneContainer` Klasse ist eine grundlegende Komponente des von MFC implementierten andockmodells. Ein Objekt dieser Klasse speichert Zeiger in zwei andockbare Bereiche oder zwei Instanzen von `CPaneContainer.`. Es speichert auch einen Zeiger auf den Unterteiler, der die Bereiche (oder die Container) trennt. Durch das Verschachteln von Containern ineinander kann das Framework eine binären Struktur erstellen, die komplexe Andocklayouts darstellt. Der Stamm der binären Struktur befindet sich in einem [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md) Objekt.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
 
## <a name="syntax"></a>Syntax  
  
```  
class CPaneContainer : public CObject    
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneContainer::CPaneContainer](#cpanecontainer)|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneContainer::AddPane](#addpane)||  
|[CPaneContainer::AddRef](#addref)||  
|[CPaneContainer::AddSubPaneContainer](#addsubpanecontainer)||  
|[CPaneContainer::CalcAvailablePaneSpace](#calcavailablepanespace)||  
|[CPaneContainer::CalcAvailableSpace](#calcavailablespace)||  
|[CPaneContainer::CalculateRecentSize](#calculaterecentsize)||  
|[CPaneContainer::CheckPaneDividerVisibility](#checkpanedividervisibility)||  
|[CPaneContainer::Copy](#copy)||  
|[CPaneContainer::DeletePane](#deletepane)||  
|[CPaneContainer::FindSubPaneContainer](#findsubpanecontainer)||  
|[CPaneContainer::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainer::GetAssociatedSiblingPaneIDs](#getassociatedsiblingpaneids)||  
|[CPaneContainer::GetLeftPane](#getleftpane)||  
|[CPaneContainer::GetLeftPaneContainer](#getleftpanecontainer)||  
|[CPaneContainer::GetMinSize](#getminsize)||  
|[CPaneContainer::GetMinSizeLeft](#getminsizeleft)||  
|[CPaneContainer::GetMinSizeRight](#getminsizeright)||  
|[CPaneContainer::GetNodeCount](#getnodecount)||  
|[CPaneContainer::GetPaneDivider](#getpanedivider)||  
|[CPaneContainer::GetParentPaneContainer](#getparentpanecontainer)||  
|[CPaneContainer::GetRecentPaneDividerRect](#getrecentpanedividerrect)||  
|[CPaneContainer::GetRecentPaneDividerStyle](#getrecentpanedividerstyle)||  
|[CPaneContainer::GetRecentPercent](#getrecentpercent)||  
|[CPaneContainer::GetRefCount](#getrefcount)||  
|[CPaneContainer::GetResizeStep](#getresizestep)||  
|[CPaneContainer::GetRightPane](#getrightpane)||  
|[CPaneContainer::GetRightPaneContainer](#getrightpanecontainer)||  
|[CPaneContainer::GetTotalReferenceCount](#gettotalreferencecount)||  
|[CPaneContainer::GetWindowRect](#getwindowrect)||  
|[CPaneContainer::IsDisposed](#isdisposed)||  
|[CPaneContainer::IsEmpty](#isempty)||  
|[CPaneContainer::IsLeftPane](#isleftpane)||  
|[CPaneContainer::IsLeftPaneContainer](#isleftpanecontainer)||  
|[CPaneContainer::IsLeftPartEmpty](#isleftpartempty)||  
|[CPaneContainer::IsRightPartEmpty](#isrightpartempty)||  
|[CPaneContainer::IsVisible](#isvisible)||  
|[CPaneContainer::Move](#move)||  
|[CPaneContainer::OnDeleteHidePane](#ondeletehidepane)||  
|[CPaneContainer::OnMoveInternalPaneDivider](#onmoveinternalpanedivider)||  
|[CPaneContainer::OnShowPane](#onshowpane)||  
|[CPaneContainer::Release](#release)||  
|[CPaneContainer::ReleaseEmptyPaneContainer](#releaseemptypanecontainer)||  
|[CPaneContainer::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainer::RemovePane](#removepane)||  
|[CPaneContainer::Resize](#resize)||  
|[CPaneContainer::ResizePane](#resizepane)||  
|[CPaneContainer::ResizePartOfPaneContainer](#resizepartofpanecontainer)||  
|[CPaneContainer::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CPaneContainer::SetPane](#setpane)||  
|[CPaneContainer::SetPaneContainer](#setpanecontainer)||  
|[CPaneContainer::SetPaneDivider](#setpanedivider)||  
|[CPaneContainer::SetParentPaneContainer](#setparentpanecontainer)||  
|[CPaneContainer::SetRecentPercent](#setrecentpercent)||  
|[CPaneContainer::SetUpByID](#setupbyid)||  
|[CPaneContainer::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneContainer::StretchPaneContainer](#stretchpanecontainer)||  
  
### <a name="remarks"></a>Hinweise  
 `CPaneContainer`Objekte werden automatisch vom Framework erstellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Instanz erstellen die `CPaneContainer` Klasse. Dieser Codeausschnitt ist Teil der [Fenstergröße festgelegt Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#2;](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize&#1;](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainer](../../mfc/reference/cpanecontainer-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpanecontainer.h  
  
##  <a name="addpane"></a>CPaneContainer::AddPane  

  
```  
CDockablePane* AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addref"></a>CPaneContainer::AddRef  

  
```  
void AddRef();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addsubpanecontainer"></a>CPaneContainer::AddSubPaneContainer  

  
```  
BOOL AddSubPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bRightNodeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pContainer`  
 [in] `bRightNodeNew`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcavailablepanespace"></a>CPaneContainer::CalcAvailablePaneSpace  

  
```  
virtual int CalcAvailablePaneSpace(
    int nRequiredOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRequiredOffset`  
 [in] `pBar`  
 [in] `pContainer`  
 [in] `bLeftBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcavailablespace"></a>CPaneContainer::CalcAvailableSpace  

  
```  
virtual CSize CalcAvailableSpace(
    CSize sizeStretch,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `sizeStretch`  
 [in] `bLeftBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calculaterecentsize"></a>CPaneContainer::CalculateRecentSize  

  
```  
void CalculateRecentSize();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="checkpanedividervisibility"></a>CPaneContainer::CheckPaneDividerVisibility  

  
```  
void CheckPaneDividerVisibility();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copy"></a>CPaneContainer::Copy  

  
```  
virtual CPaneContainer* Copy(CPaneContainer* pParentContainer);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentContainer`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cpanecontainer"></a>CPaneContainer::CPaneContainer  

  
```  
CPaneContainer(
    CPaneContainerManager* pManager = NULL,  
    CDockablePane* pLeftBar = NULL,  
    CDockablePane* pRightBar = NULL,  
    CPaneDivider* pSlider = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pManager`  
 [in] `pLeftBar`  
 [in] `pRightBar`  
 [in] `pSlider`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="deletepane"></a>CPaneContainer::DeletePane  

  
```  
virtual void DeletePane(
    CDockablePane* pBar,  
    BC_FIND_CRITERIA barType);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `barType`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findsubpanecontainer"></a>CPaneContainer::FindSubPaneContainer  

  
```  
CPaneContainer* FindSubPaneContainer(
    const CObject* pObject,  
    BC_FIND_CRITERIA findCriteria);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pObject`  
 [in] `findCriteria`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findtabbedpane"></a>CPaneContainer::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getassociatedsiblingpaneids"></a>CPaneContainer::GetAssociatedSiblingPaneIDs  

  
```  
CList<UINT, UINT>* GetAssociatedSiblingPaneIDs(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getleftpane"></a>CPaneContainer::GetLeftPane  

  
```  
const CDockablePane* GetLeftPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getleftpanecontainer"></a>CPaneContainer::GetLeftPaneContainer  

  
```  
const CPaneContainer* GetLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getminsize"></a>CPaneContainer::GetMinSize  

  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `size`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getminsizeleft"></a>CPaneContainer::GetMinSizeLeft  

  
```  
virtual void GetMinSizeLeft(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `size`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getminsizeright"></a>CPaneContainer::GetMinSizeRight  

  
```  
virtual void GetMinSizeRight(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `size`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getnodecount"></a>CPaneContainer::GetNodeCount  

  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanedivider"></a>CPaneContainer::GetPaneDivider  

  
```  
const CPaneDivider* GetPaneDivider() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentpanecontainer"></a>CPaneContainer::GetParentPaneContainer  

  
```  
CPaneContainer* GetParentPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrecentpanedividerrect"></a>CPaneContainer::GetRecentPaneDividerRect  

  
```  
CRect GetRecentPaneDividerRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrecentpanedividerstyle"></a>CPaneContainer::GetRecentPaneDividerStyle  

  
```  
DWORD GetRecentPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrecentpercent"></a>CPaneContainer::GetRecentPercent  

  
```  
int GetRecentPercent();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrefcount"></a>CPaneContainer::GetRefCount  

  
```  
LONG GetRefCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getresizestep"></a>CPaneContainer::GetResizeStep  

  
```  
virtual int GetResizeStep() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrightpane"></a>CPaneContainer::GetRightPane  

  
```  
const CDockablePane* GetRightPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrightpanecontainer"></a>CPaneContainer::GetRightPaneContainer  

  
```  
const CPaneContainer* GetRightPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettotalreferencecount"></a>CPaneContainer::GetTotalReferenceCount  

  
```  
int GetTotalReferenceCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getwindowrect"></a>CPaneContainer::GetWindowRect  

  
```  
virtual void GetWindowRect(
    CRect& rect,  
    BOOL bIgnoreVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 [in] `bIgnoreVisibility`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdisposed"></a>CPaneContainer::IsDisposed  

  
```  
BOOL IsDisposed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isempty"></a>CPaneContainer::IsEmpty  

  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isleftpane"></a>CPaneContainer::IsLeftPane  

  
```  
BOOL IsLeftPane(CDockablePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isleftpanecontainer"></a>CPaneContainer::IsLeftPaneContainer  

  
```  
BOOL IsLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isleftpartempty"></a>CPaneContainer::IsLeftPartEmpty  

  
```  
BOOL IsLeftPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCheckVisibility`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isrightpartempty"></a>CPaneContainer::IsRightPartEmpty  

  
```  
BOOL IsRightPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCheckVisibility`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isvisible"></a>CPaneContainer::IsVisible  

  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="move"></a>CPaneContainer::Move  

  
```  
virtual void Move(CPoint ptNewLeftTop);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptNewLeftTop`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondeletehidepane"></a>CPaneContainer::OnDeleteHidePane  

  
```  
void OnDeleteHidePane(
    CDockablePane* pBar,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `bHide`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmoveinternalpanedivider"></a>CPaneContainer::OnMoveInternalPaneDivider  

  
```  
virtual int OnMoveInternalPaneDivider(
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 [in] `hdwp`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowpane"></a>CPaneContainer::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `bShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="release"></a>CPaneContainer::Release  

  
```  
DWORD Release();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="releaseemptypanecontainer"></a>CPaneContainer::ReleaseEmptyPaneContainer  

  
```  
void ReleaseEmptyPaneContainer();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removenonvalidpanes"></a>CPaneContainer::RemoveNonValidPanes  

  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removepane"></a>CPaneContainer::RemovePane  

  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="resize"></a>CPaneContainer::Resize  

  
```  
virtual void Resize(
    CRect rect,  
    HDWP& hdwp,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 [in] `hdwp`  
 [in] `bRedraw`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="resizepane"></a>CPaneContainer::ResizePane  

  
```  
virtual void ResizePane(
    int nOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bHorz,  
    BOOL bLeftBar,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 [in] `pBar`  
 [in] `pContainer`  
 [in] `bHorz`  
 [in] `bLeftBar`  
 [in] `hdwp`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="resizepartofpanecontainer"></a>CPaneContainer::ResizePartOfPaneContainer  

  
```  
virtual void ResizePartOfPaneContainer(
    int nOffset,  
    BOOL bLeftPart,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 [in] `bLeftPart`  
 [in] `hdwp`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="serialize"></a>CPaneContainer::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpane"></a>CPaneContainer::SetPane  

  
```  
void SetPane(
    CDockablePane* pBar,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `bLeft`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanecontainer"></a>CPaneContainer::SetPaneContainer  

  
```  
void SetPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pContainer`  
 [in] `bLeft`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanedivider"></a>CPaneContainer::SetPaneDivider  

  
```  
void SetPaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pSlider`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setparentpanecontainer"></a>CPaneContainer::SetParentPaneContainer  

  
```  
void SetParentPaneContainer(CPaneContainer* p);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `p`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setrecentpercent"></a>CPaneContainer::SetRecentPercent  

  
```  
void SetRecentPercent(int nRecentPercent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRecentPercent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setupbyid"></a>CPaneContainer::SetUpByID  

  
```  
BOOL SetUpByID(
    UINT nID,  
    CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 [in] `pBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneContainer::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="stretchpanecontainer"></a>CPaneContainer::StretchPaneContainer  

  
```  
virtual int StretchPaneContainer(
    int nOffset,  
    BOOL bStretchHorz,  
    BOOL bLeftBar,  
    BOOL bMoveSlider,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 [in] `bStretchHorz`  
 [in] `bLeftBar`  
 [in] `bMoveSlider`  
 [in] `hdwp`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CPaneContainerManager-Klasse](../../mfc/reference/cpanecontainermanager-class.md)

