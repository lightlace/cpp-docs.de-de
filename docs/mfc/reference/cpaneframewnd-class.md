---
title: CPaneFrameWnd Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6846f50b0e89193992a42ea50e785009f31e6d19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378786"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Implementiert ein Minirahmenfenster, das einen Bereich enthält. Der Bereich füllt den Clientbereich des Fensters aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|Fügt einen Bereich hinzu.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|Fügt einen Bereich zur globalen Liste hinzu oder entfernt ihn daraus.|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|Passt das Layout des Minirahmenfensters an.|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Berechnet die Größe der Rahmen für ein Minirahmenfenster.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Berechnet das erwartete Rechteck eines angedockten Fensters.|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Bestimmt, ob der aktuelle Bereich an einen anderen Bereich oder an ein Framefenster angedockt werden kann.|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Bestimmt, ob das Minirahmenfenster an einen Bereich angedockt werden kann.|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert den Bereich in ein Dokument mit Registerkarten.|  
|[CPaneFrameWnd::Create](#create)|Erstellt ein Minirahmenfenster und fügt es dem `CPaneFrameWnd`-Objekt an.|  
|[CPaneFrameWnd::CreateEx](#createex)|Erstellt ein Minirahmenfenster und fügt es dem `CPaneFrameWnd`-Objekt an.|  
|[CPaneFrameWnd::DockPane](#dockpane)|Dockt den Bereich an.|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Sucht einen Bereich mit der angegebenen Steuerelement-ID in der globalen Liste unverankerter Bereiche.|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Sucht das Minirahmenfenster mit einem vom Benutzer angegebenen Punkt.|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe der Beschriftung des Minirahmenfensters zurück.|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Berechnet das umschließende Rechteck der Beschriftung eines Minirahmenfensters.|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Gibt den Beschriftungstext zurück.|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Gibt den Andockmodus zurück.|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Gibt den ersten sichtbaren Bereich zurück, der in einem Minirahmenfenster enthalten ist.|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|Gibt einen Bereich zurück, der im Minirahmenfenster enthalten ist.|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Gibt die Anzahl der Bereiche zurück, die im Minirahmenfenster enthalten sind.|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Gibt die Anzahl der sichtbaren Bereiche zurück, die im Minirahmenfenster enthalten sind.|  
|[CPaneFrameWnd::HitTest](#hittest)|Bestimmt, welcher Teil eines Minirahmenfensters sich an einem bestimmten Punkt befindet.|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Bestimmt, ob ein Minirahmenfenster abwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|Bestimmt, ob ein Minirahmenfenster aufwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Hält den Andocktimer an.|  
|[CPaneFrameWnd::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung.|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Bestimmt, ob Andocken möglich ist.|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Dockt das Minirahmenfenster an der letzten Position an.|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Hält den Rolluptimer an.|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Verschiebt das Minirahmenfenster anhand eines angegebenen Offsets.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Passt das Layout eines enthaltenen Bereichs an.|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Richtet den Rolluptimer ein.|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Wird vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird.|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Gibt einen Bereich zurück, wenn er einen vom Benutzer angegebenen Punkt innerhalb einer Minirahmenfensters enthält.|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden.|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|Zeichnet alle Minirahmenfenster neu.|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Wird vom Framework aufgerufen, um ungültige Bereiche zu entfernen.|  
|[CPaneFrameWnd::RemovePane](#removepane)|Entfernt einen Bereich aus dem Minirahmenfenster.|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|Ersetzt einen Bereich durch einen anderen.|  
|[CPaneFrameWnd::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung.|  
|`CPaneFrameWnd::Serialize`|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Legt Beschriftungsschaltflächen fest.|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Legt den Andocktimer fest.|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|Legt den Andockzustand fest.|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Wird vom Framework aufgerufen, um den Zustand vor dem Andocken festzulegen.|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Passt die Größe eines Minirahmenfensters an, damit es in der Größe einem enthaltenen Bereich entspricht.|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Schneidet ein Menü ab.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Bestimmt, ob ein Minirahmenfenster aufwärts oder abwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Zeichnet die Rahmen eines Minirahmenfensters.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Gibt an, ob die Fensterklasse mit dem `CS_SAVEBITS`-Klassenformat registriert werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Das Framework erstellt automatisch ein `CPaneFrameWnd`-Objekt, wenn ein Bereich aus einem angedockten Zustand in einen unverankerten Zustand wechselt.  
  
 Ein Minirahmenfenster kann mit sichtbarem Inhalt (sofortiges Andocken) oder mit einem Rechteck (standardmäßiges Andocken) gezogen werden. Der Andockmodus des Containerbereichs des Minirahmenfensters bestimmt das Ziehverhalten des Minirahmens. Weitere Informationen finden Sie unter [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
 Ein Minirahmenfenster zeigt Schaltflächen auf der Beschriftung in Übereinstimmung mit den enthaltenen Bereichsformat an. Wenn der Bereich geschlossen werden kann ( [cbasepane:: Canbeclosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), eine Schaltfläche "Schließen" angezeigt. Wenn der Bereich das `AFX_CBRS_AUTO_ROLLUP`-Format aufweist, wird ein Pin angezeigt.  
  
 Wenn Sie eine Klasse von `CPaneFrameWnd` ableiten, müssen Sie dem Framework die Erstellung erläutern. Erstellen Sie die Klasse durch Überschreiben [cpane:: Createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), oder legen Sie die `CPane::m_pMiniFrameRTC` Member so fest, dass die It auf die laufzeitklasseninformationen für die Klasse verweist.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>  CPaneFrameWnd::AddPane  
 Fügt einen Bereich hinzu.  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Der Bereich hinzufügen.  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 Fügt einen Bereich zur globalen Liste hinzu oder entfernt ihn daraus.  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Der Bereich zum Hinzufügen oder entfernen.  
  
 [in] `bAdd`  
 Wenn ungleich 0 (null) ist, fügen Sie den Bereich hinzu. Bei 0, entfernen Sie den Bereich an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ausgeführt wurde; andernfalls 0.  
  
##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout  
 Passt das Layout des Minirahmenfensters an.  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize  
 Berechnet die Größe der Rahmen für ein Minirahmenfenster.  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectBorderSize`  
 Enthält die Größe in Pixel des Rahmens, der das Minirahmenfenster an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework zum Berechnen der Größe des Rands des ein Minirahmenfenster aufgerufen. Die zurückgegebene Größe hängt davon ab, ob ein Minirahmenfenster eine Symbolleiste enthält oder eine [CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect  
 Berechnet das erwartete Rechteck eines angedockten Fensters.  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndToDock`  
 Ein Zeiger auf das Fenster angedockt.  
  
 [in] `ptMouse`  
 Die Position des Mauszeigers.  
  
 [out] `rectResult`  
 Das berechnete Rechteck.  
  
 [out] `bDrawTab`  
 Wenn `TRUE`, zeichnen Sie eine Registerkarte. Wenn `FALSE`, zeichnen Sie eine Registerkarte nicht.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf den Zielbereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet das Rechteck, das ein Fenster einnehmen würde, wenn ein Benutzer das Fenster zu den vom angegebenen Punkt gezogen haben `ptMouse` und er es angedockt.  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 Bestimmt, ob der aktuelle Bereich an einen anderen Bereich oder an ein Framefenster angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich kann, zu einem anderen Bereich oder der Zielframe, Fenster angedockt werden; andernfalls `FALSE`.  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 Bestimmt, ob das Minirahmenfenster an einen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockingBar`  
 Ein Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Minirahmenfensters an angedockt werden kann `pDockingBar`, andernfalls 0.  
  
##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument  
 Konvertiert den Bereich in ein Dokument mit Registerkarten.  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>  CPaneFrameWnd::Create  
 Erstellt ein Minirahmenfenster und fügt es der [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszWindowName`  
 Gibt den Text auf dem Minirahmenfenster angezeigt werden sollen.  
  
 [in] `dwStyle`  
 Gibt den Fensterstil. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der das Minirahmenfenster an.  
  
 [in] [out] `pParentWnd`  
 Gibt den übergeordneten Frame, der das Minirahmenfenster an. Dieser Wert darf nicht sein `NULL`.  
  
 [in] [out] `pContext`  
 Gibt eine benutzerdefinierte Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Minirahmenfenster wird in zwei Schritten erstellt. Zunächst erstellt das Framework eine `CPaneFrameWnd` Objekt. Zweitens, ruft er `Create` zum Erstellen von Windows-Minirahmenfenster und fügen Sie es auf die `CPaneFrameWnd` Objekt.  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 Erstellt ein Minirahmenfenster und fügt es der [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyleEx`  
 Gibt den erweiterten Fensterstil. Weitere Informationen finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in] `lpszWindowName`  
 Gibt den Text auf dem Minirahmenfenster angezeigt werden sollen.  
  
 [in] `dwStyle`  
 Gibt den Fensterstil. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der das Minirahmenfenster an.  
  
 [in] [out] `pParentWnd`  
 Gibt den übergeordneten Frame, der das Minirahmenfenster an. Dieser Wert darf nicht sein `NULL`.  
  
 [in] [out] `pContext`  
 Gibt eine benutzerdefinierte Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Minirahmenfenster wird in zwei Schritten erstellt. Zunächst erstellt das Framework eine `CPaneFrameWnd` Objekt. Zweitens, ruft er `Create` zum Erstellen von Windows-Minirahmenfenster und fügen Sie es auf die `CPaneFrameWnd` Objekt.  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 Dockt den Bereich an.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `bWasDocked`  
 `TRUE` Wenn der Bereich bereits angedockt wurde; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Vorgang erfolgreich war, die `CDockablePane` , dass der Bereich, andernfalls angedockt wurde `NULL`.  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 Sucht einen Bereich mit der angegebenen Steuerelement-ID in der globalen Liste unverankerter Bereiche.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Stellt die Steuerelement-ID des Bereichs zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich mit der ID angegebene Steuerelement; andernfalls `NULL`, besitzt keine Bereich die angegebenen Steuerelement-ID.  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 Sucht das Minirahmenfenster an, das den angegebenen Punkt enthält.  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Der Punkt in Bildschirmkoordinaten.  
  
 [in] `nSensitivity`  
 Erhöhen Sie den Suchbereich des Minirahmenfenster, indem Sie diese Größe. Ein Minirahmenfenster erfüllt die Suchkriterien, fällt der angegebene Punkt in der höheren Bereich.  
  
 [in] `pFrameToExclude`  
 Gibt ein Minirahmenfenster der Suche ausgeschlossen.  
  
 [in] `bFloatMultiOnly`  
 Wenn `TRUE`, nur suchen Minirahmenfenster haben die `CBRS_FLOAT_MULTI` Stil. Wenn `FALSE`, suchen Sie alle Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Minirahmenfenster an, die enthält `pt`andernfalls `NULL`.  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 Gibt die Höhe der Beschriftung des Minirahmenfensters zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der das Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Höhe des ein Minirahmenfenster zu bestimmen. Die Höhe wird standardmäßig auf festgelegt `SM_CYSMCAPTION`. Weitere Informationen finden Sie unter [GetSystemMetrics Funktion](http://msdn.microsoft.com/library/windows/desktop/ms724385).  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 Berechnet das umschließende Rechteck der Beschriftung eines Minirahmenfensters.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectCaption`  
 Enthält die Größe und Position von der Beschriftung des Minirahmenfensters in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework berechnet das umschließende Rechteck der Beschriftung einer Minirahmenfensters aufgerufen.  
  
##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText  
 Gibt den Beschriftungstext zurück.  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Beschriftungstext des Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn es sich um den Beschriftungstext anzeigt.  
  
##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode  
 Gibt den Andockmodus zurück.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Andockmodus. Einer der folgenden Werte:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 Gibt den ersten sichtbaren Bereich zurück, der in einem Minirahmenfenster enthalten ist.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Bereich in das Minirahmenfenster oder `NULL` , wenn das Minirahmenfenster keine Bereiche enthält.  
  
##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpane"></a>  CPaneFrameWnd::GetPane  
 Gibt einen Bereich zurück, der im Minirahmenfenster enthalten ist.  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich, der in der Minirahmenfensters enthalten ist oder `NULL` , wenn das Minirahmenfenster keine Bereiche enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 Gibt die Anzahl der Bereiche zurück, die im Minirahmenfenster enthalten sind.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bereiche im Minirahmenfenster. Dieser Wert kann 0 (null) sein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparent"></a>  CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount  
 Gibt die Anzahl der sichtbaren Bereiche zurück, die im Minirahmenfenster enthalten sind.  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der sichtbaren Bereiche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hittest"></a>  CPaneFrameWnd::HitTest  
 Bestimmt, welcher Teil eines Minirahmenfensters sich an einem bestimmten Punkt befindet.  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der Punkt zu testen.  
  
 [in] `bDetectCaption`  
 Wenn `TRUE`, überprüfen Sie den Punkt für die Beschriftung. Wenn `FALSE`, ignorieren Sie die Beschriftung.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`HTNOWHERE`|Der Punkt ist außerhalb der Minirahmenfenster.|  
|`HTCLIENT`|Der Punkt ist im Clientbereich.|  
|`HTCAPTION`|Der Punkt ist auf der Beschriftung.|  
|`HTTOP`|Der Punkt befindet sich oben.|  
|`HTTOPLEFT`|Der Punkt ist an der oberen linken Ecke.|  
|`HTTOPRIGHT`|Der Punkt ist oben rechts auf.|  
|`HTLEFT`|Der Punkt ist auf der linken Seite.|  
|`HTRIGHT`|Der Punkt ist auf der rechten Seite.|  
|`HTBOTTOM`|Der Punkt wird im unteren Bereich.|  
|`HTBOTTOMLEFT`|Der Punkt ist links unten.|  
|`HTBOTTOMRIGHT`|Der Punkt ist unten rechts.|  
  
##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown  
 Bestimmt, ob ein Minirahmenfenster abwärts zugeordnet werden soll.  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Minirahmenfenster abwärts zugeordnet werden muss; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu bestimmen, ob ein Minirahmenfenster abwärts zugeordnet werden soll. Das Rollup/Rolldownschaltfläche-Feature ist für ein Minirahmenfenster aktiviert, wenn es über mindestens einen Bereich enthält, die `AFX_CBRS_AUTO_ROLLUP` Flag. Dieses Flag wird festgelegt, wenn ein Bereich erstellt wird. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Standardmäßig überprüft das Framework an, ob der Mauszeiger die Form ist innerhalb des Minirahmenfensters Fenster umschließenden Rechtecks bestimmt, ob das Fenster abwärts zugeordnet werden. Sie können dieses Verhalten in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 Bestimmt, ob ein Minirahmenfenster aufwärts zugeordnet werden soll.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Minirahmenfenster gemacht werden muss; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um festzustellen, ob ein Minirahmenfenster gemacht werden soll. Das Rollup/Rolldownschaltfläche-Feature ist für ein Minirahmenfenster aktiviert, wenn es über mindestens einen Bereich enthält, die `AFX_CBRS_AUTO_ROLLUP` Flag. Dieses Flag wird festgelegt, wenn ein Bereich erstellt wird. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Standardmäßig überprüft das Framework an, ob der Mauszeiger die Form ist innerhalb des Minirahmenfensters Fenster umschließenden Rechtecks bestimmt, ob das Fenster gemacht werden. Sie können dieses Verhalten in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer  
 Hält den Andocktimer an.  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Profilname.  
  
 [in] `uiID`  
 Der Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich Zustand erfolgreich geladen wurde; andernfalls `FALSE`.  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 Gibt an, ob die Fensterklasse registriert, die verfügt die `CS_SAVEBITS` -Klassenstil.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses statische Element auf `TRUE` Minirahmenfensters Fensterklasse registrieren, die verfügt die `CS_SAVEBITS` Stil. Dies hilft möglicherweise verringern Flimmern, wenn ein Benutzer das Minirahmenfenster zieht.  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 Bestimmt, ob Andocken möglich ist.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` ob Andocken möglich ist; andernfalls `FALSE`.  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 Bestimmt, ob ein Minirahmenfenster aufwärts oder abwärts zugeordnet werden soll.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework, um zu bestimmen, ob ein Minirahmenfenster nach oben oder unten von neuem beginnen soll.  
  
 Wird standardmäßig das Framework ruft [CPaneFrameWnd::IsRollUp](#isrollup) und [CPaneFrameWnd::IsRollDown](#isrolldown) und gestreckt wird, oder das Minirahmenfenster wiederhergestellt. Sie können diese Methode in einer abgeleiteten Klasse zum Verwenden eines anderen visuellen Effekts überschreiben.  
  
##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos  
 Dockt das Minirahmenfenster an der letzten Position an.  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder  
 Zeichnet die Rahmen eines Minirahmenfensters.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der zum Zeichnen des Rahmens.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework zum Zeichnen der Rahmen von Minirahmenfenster aufgerufen.  
  
##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer  
 Hält den Rolluptimer an.  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane  
 Verschiebt das Minirahmenfenster anhand eines angegebenen Offsets.  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich (ignoriert).  
  
 [in] `ptOffset`  
 Der Offset, um den Bereich zu verschieben.  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 Passt das Layout eines Bereichs innerhalb eines Minirahmenfensters.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn das Layout eines Bereichs in das Minirahmenfenster angepasst werden muss.  
  
 Standardmäßig wird im Bereich positioniert, um den vollständigen Clientbereich des Fensters Minirahmenfensters abzudecken.  
  
##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer  
 Richtet den Rolluptimer ein.  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane  
 Wird vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird.  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Der Bereich, die angezeigt oder ausgeblendet.  
  
 [in] `bShow`  
 `TRUE` Wenn der Bereich angezeigt wird; `FALSE` Wenn der Bereich ausgeblendet ist.  
  
### <a name="remarks"></a>Hinweise  
 Vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPin`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint  
 Gibt einen Bereich zurück, wenn er einen vom Benutzer angegebenen Punkt innerhalb einer Minirahmenfensters enthält.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der Punkt, die der Benutzer geklickt hat, in Bildschirmkoordinaten.  
  
 [in] `nSensitivity`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `bCheckVisibility`  
 `TRUE` um anzugeben, dass nur sichtbaren Bereiche zurückgegeben werden sollen; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich, der der Benutzer geklickt hat, oder `NULL` Wenn kein Bereich an diesem Speicherort vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich zu erhalten, der den angegebenen Punkt enthält.  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 Zeichnet alle Minirahmenfenster neu.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert alle Minirahmenfenster durch Aufrufen von [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) für jedes Fenster.  
  
##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes  
 Wird vom Framework aufgerufen, um ungültige Bereiche zu entfernen.  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane  
 Entfernt einen Bereich aus dem Minirahmenfenster.  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf den Bereich zu entfernen.  
  
 [in] `bDestroy`  
 Gibt an, was geschieht, um das Minirahmenfenster. Wenn `bDestroy` ist `TRUE`, diese Methode zerstört das Minirahmenfenster sofort. Ist er `FALSE`, diese Methode zerstört das Minirahmenfenster nach einer bestimmten Verzögerung.  
  
 [in] `bNoDelayedDestroy`  
 Wenn `TRUE`, verzögert Zerstörung ist deaktiviert. Wenn `FALSE`, verzögert Zerstörung aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework zerstören Minirahmenfenster kann sofort oder nach einer bestimmten Verzögerung. Wenn Sie Zerstörung von Minirahmenfenster verzögern möchten, übergeben Sie `FALSE` in der `bNoDelayedDestroy` Parameter. Verzögerte Zerstörung auftritt, wenn das Framework verarbeitet die `AFX_WM_CHECKEMPTYMINIFRAME` Nachricht.  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 Ersetzt einen Bereich durch einen anderen.  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBarOrg`  
 Ein Zeiger auf den ursprünglichen Bereich.  
  
 [in] `pBarReplaceWith`  
 Ein Zeiger auf den Bereich, der den ursprünglichen Bereich ersetzt.  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Profilname.  
  
 [in] `uiID`  
 Der Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Zustand des Bereichs erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 Legt Beschriftungsschaltflächen fest.  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwButtons`  
 Bitweise OR-Kombination der folgenden Werte:  
  
- `AFX_CAPTION_BTN_CLOSE`  
  
- `AFX_CAPTION_BTN_PIN`  
  
- `AFX_CAPTION_BTN_MENU`  
  
- `AFX_CAPTION_BTN_CUSTOMIZE`  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelayShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pManager`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 Legt den Andocktimer fest.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTimeOut`  
 Der Timeoutwert in Millisekunden.  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 Legt den Andockzustand fest.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockManager`  
 Ein Zeiger auf eine Dock-Manager.  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptNew`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState  
 Wird vom Framework aufgerufen, um den Zustand vor dem Andocken festzulegen.  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `preDockState`  
 Mögliche Werte:  
  
- `PDS_NOTHING`,  
  
- `PDS_DOCK_REGULAR`,  
  
- `PDS_DOCK_TO_TAB`  
  
 [in] `pBarToDock`  
 Ein Zeiger auf den Bereich angedockt.  
  
 [in] `dockMethod`  
 Die Andock-Methode. (Dieser Parameter wird ignoriert).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Minirahmenfenster nicht angedockter ist. `FALSE` , wenn der Bereich angedockt ist.  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 Passt die Größe eines Minirahmenfensters an, sodass sie einem enthaltenen Bereich entspricht.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Größe eines Minirahmenfensters auf die Größe eines enthaltenen Bereichs anpassen.  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 Schneidet ein Menü ab.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Ein Zeiger auf ein Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockingBar`  
 [in] `pTabbedBar`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)
