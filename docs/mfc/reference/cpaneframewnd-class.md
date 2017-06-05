---
title: Klasse CPaneFrameWnd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CPaneFrameWnd class
- Serialize method
- PreTranslateMessage method
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a8609643a9e64127af1d8035c496cedab4b1b1e9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Implementiert ein Minirahmenfenster, das einen Bereich enthält. Der Bereich füllt den Clientbereich des Fensters aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|`CPaneFrameWnd::PreTranslateMessage`|Von der Klasse verwendet [CWinApp](../../mfc/reference/cwinapp-class.md) auf fenstermeldungen zu übersetzen, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen.|  
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
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Gibt an, ob die Fensterklasse mit dem `CS_SAVEBITS`-Klassenformat registriert werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Das Framework erstellt automatisch ein `CPaneFrameWnd`-Objekt, wenn ein Bereich aus einem angedockten Zustand in einen unverankerten Zustand wechselt.  
  
 Ein Minirahmenfenster kann mit sichtbarem Inhalt (sofortiges Andocken) oder mit einem Rechteck (standardmäßiges Andocken) gezogen werden. Der Andockmodus des Containerbereichs des Minirahmenfensters bestimmt das Ziehverhalten des Minirahmens. Weitere Informationen finden Sie unter [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
 Ein Minirahmenfenster zeigt Schaltflächen auf der Beschriftung in Übereinstimmung mit den enthaltenen Bereichsformat an. Wenn der Bereich geschlossen werden kann ( [cbasepane:: Canbeclosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), eine Schaltfläche "Schließen" angezeigt. Wenn der Bereich das `AFX_CBRS_AUTO_ROLLUP`-Format aufweist, wird ein Pin angezeigt.  
  
 Wenn Sie eine Klasse von `CPaneFrameWnd` ableiten, müssen Sie dem Framework die Erstellung erläutern. Erstellen Sie die Klasse durch Überschreiben [cpane:: Createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), oder legen Sie die `CPane::m_pMiniFrameRTC` Member so fest, dass die It auf die Laufzeit-Klasseninformationen für die Klasse verweist.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>CPaneFrameWnd::AddPane  
 Fügt einen Bereich hinzu.  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Der Bereich hinzufügen.  
  
##  <a name="addremovepanefromgloballist"></a>CPaneFrameWnd::AddRemovePaneFromGlobalList  
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
 Wenn nicht NULL ist, fügen Sie im Bereich. Entfernen Sie im Bereich bei 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; andernfalls 0.  
  
##  <a name="adjustlayout"></a>CPaneFrameWnd::AdjustLayout  
 Passt das Layout des Minirahmenfensters an.  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcbordersize"></a>CPaneFrameWnd::CalcBorderSize  
 Berechnet die Größe des Rahmens für ein Minirahmenfenster.  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectBorderSize`  
 Die Größe in Pixel des Rahmens der Minirahmenfenster enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework zum Berechnen der Größe des Rahmens für ein Minirahmenfenster aufgerufen. Die zurückgegebene Größe hängt davon ab, ob ein Minirahmenfenster eine Symbolleiste enthält oder eine [CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
##  <a name="calcexpecteddockedrect"></a>CPaneFrameWnd::CalcExpectedDockedRect  
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
 Wenn `TRUE`, zeichnen Sie eine Registerkarte. Wenn `FALSE`, eine Registerkarte nicht darstellen.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf den Zielbereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet das Rechteck, das ein Fenster einnehmen würde, wenn ein Benutzer das Fenster durch festgelegten Punkt gezogen `ptMouse` und es gibt es angedockt.  
  
##  <a name="canbeattached"></a>CPaneFrameWnd::CanBeAttached  
 Bestimmt, ob der aktuelle Bereich an einen anderen Bereich oder an ein Framefenster angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich zu einem anderen Bereich oder Fenster angedockt werden kann andernfalls `FALSE`.  
  
##  <a name="canbedockedtopane"></a>CPaneFrameWnd::CanBeDockedToPane  
 Bestimmt, ob das Minirahmenfenster an einen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockingBar`  
 Einen Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die kleinen Rahmenfenster angedockt werden kann `pDockingBar`; andernfalls 0.  
  
##  <a name="checkgrippervisibility"></a>CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="converttotabbeddocument"></a>CPaneFrameWnd::ConvertToTabbedDocument  
 Konvertiert den Bereich in ein Dokument mit Registerkarten.  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>CPaneFrameWnd::Create  
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
 Gibt den Text auf der Minirahmenfenster angezeigt.  
  
 [in] `dwStyle`  
 Gibt den Fensterstil. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der das Minirahmenfenster an.  
  
 [in] [out]`pParentWnd`  
 Gibt den übergeordneten Frame das Minirahmenfenster an. Dieser Wert darf nicht sein `NULL`.  
  
 [in] [out]`pContext`  
 Gibt den benutzerdefinierten Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Minirahmenfenster wird in zwei Schritten erstellt. Das Framework erstellt zunächst ein `CPaneFrameWnd` Objekt. Danach ruft es `Create` auf der Windows-Minirahmenfenster erstellen und Anfügen an die `CPaneFrameWnd` Objekt.  
  
##  <a name="createex"></a>CPaneFrameWnd::CreateEx  
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
 Gibt den erweiterten Fensterstil. Weitere Informationen finden Sie unter [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md)  
  
 [in] `lpszWindowName`  
 Gibt den Text auf der Minirahmenfenster angezeigt.  
  
 [in] `dwStyle`  
 Gibt den Fensterstil. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der das Minirahmenfenster an.  
  
 [in] [out]`pParentWnd`  
 Gibt den übergeordneten Frame das Minirahmenfenster an. Dieser Wert darf nicht sein `NULL`.  
  
 [in] [out]`pContext`  
 Gibt den benutzerdefinierten Kontext.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Minirahmenfenster wird in zwei Schritten erstellt. Das Framework erstellt zunächst ein `CPaneFrameWnd` Objekt. Danach ruft es `Create` auf der Windows-Minirahmenfenster erstellen und Anfügen an die `CPaneFrameWnd` Objekt.  
  
##  <a name="dockpane"></a>CPaneFrameWnd::DockPane  
 Dockt den Bereich an.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `bWasDocked`  
 `TRUE`Wenn der Bereich bereits angedockt wurde; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Vorgang erfolgreich war, die `CDockablePane` , dass der Bereich, andernfalls angedockt ist `NULL`.  
  
##  <a name="findfloatingpanebyid"></a>CPaneFrameWnd::FindFloatingPaneByID  
 Sucht einen Bereich mit der angegebenen Steuerelement-ID in der globalen Liste unverankerter Bereiche.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Stellt die Steuerelement-ID des Bereichs zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich mit der angegebenen Steuerelement-ID; andernfalls `NULL`, wenn kein Bereich die angegebene Steuerelement-ID verfügt.  
  
##  <a name="framefrompoint"></a>CPaneFrameWnd::FrameFromPoint  
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
 Erhöhen Sie den Suchbereich des Minirahmenfenster dieser Größe. Ein Minirahmenfenster erfüllt die Suchkriterien angegebene Punkt im erhöhten Bereich fällt.  
  
 [in] `pFrameToExclude`  
 Gibt ein Minirahmenfenster aus der Suche ausgeschlossen.  
  
 [in] `bFloatMultiOnly`  
 Wenn `TRUE`, sucht nur Minirahmenfenster haben die `CBRS_FLOAT_MULTI` Stil. Wenn `FALSE`, suchen Sie alle Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Minirahmenfenster, das enthält `pt`andernfalls `NULL`.  
  
##  <a name="getcaptionheight"></a>CPaneFrameWnd::GetCaptionHeight  
 Gibt die Höhe der Beschriftung des Minirahmenfensters zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Höhe des ein Minirahmenfenster zu bestimmen. Standardmäßig ist die Höhe auf festgelegt `SM_CYSMCAPTION`. Weitere Informationen finden Sie unter [GetSystemMetrics Funktion](http://msdn.microsoft.com/library/windows/desktop/ms724385).  
  
##  <a name="getcaptionrect"></a>CPaneFrameWnd::GetCaptionRect  
 Berechnet das umschließende Rechteck der Beschriftung eines Minirahmenfensters.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectCaption`  
 Enthält die Größe und Position der Beschriftung des Minirahmenfensters in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework berechnet das umschließende Rechteck der Beschriftung einer Minirahmenfensters aufgerufen.  
  
##  <a name="getcaptiontext"></a>CPaneFrameWnd::GetCaptionText  
 Gibt den Beschriftungstext zurück.  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Beschriftungstext des Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn den Beschriftungstext angezeigt.  
  
##  <a name="getdockingmanager"></a>CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdockingmode"></a>CPaneFrameWnd::GetDockingMode  
 Gibt den Andockmodus zurück.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Andockmodus. Einer der folgenden Werte:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>CPaneFrameWnd::GetFirstVisiblePane  
 Gibt den ersten sichtbaren Bereich zurück, der in einem Minirahmenfenster enthalten ist.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Bereich in das Minirahmenfenster oder `NULL` Minirahmenfenster keine Bereiche enthält.  
  
##  <a name="gethotpoint"></a>CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpane"></a>CPaneFrameWnd::GetPane  
 Gibt einen Bereich zurück, der im Minirahmenfenster enthalten ist.  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich, der in der Minirahmenfensters enthalten ist oder `NULL` Minirahmenfenster keine Bereiche enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanecount"></a>CPaneFrameWnd::GetPaneCount  
 Gibt die Anzahl der Bereiche zurück, die im Minirahmenfenster enthalten sind.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bereiche im Minirahmenfenster. Dieser Wert kann&0; (null) sein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparent"></a>CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpinstate"></a>CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrecentfloatingrect"></a>CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvisiblepanecount"></a>CPaneFrameWnd::GetVisiblePaneCount  
 Gibt die Anzahl der sichtbaren Bereiche zurück, die im Minirahmenfenster enthalten sind.  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der sichtbaren Bereiche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hittest"></a>CPaneFrameWnd::HitTest  
 Bestimmt, welcher Teil eines Minirahmenfensters sich an einem bestimmten Punkt befindet.  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der zu überprüfende Punkt.  
  
 [in] `bDetectCaption`  
 Wenn `TRUE`, überprüfen Sie den Punkt für die Beschriftung. Wenn `FALSE`, ignorieren Sie die Beschriftung.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`HTNOWHERE`|Der Punkt ist außerhalb der Minirahmenfenster.|  
|`HTCLIENT`|Der Punkt ist im Clientbereich.|  
|`HTCAPTION`|Der Punkt ist auf den Titel.|  
|`HTTOP`|Der Punkt ist am Anfang.|  
|`HTTOPLEFT`|Der Punkt ist oben links.|  
|`HTTOPRIGHT`|Der Punkt ist oben rechts.|  
|`HTLEFT`|Der Punkt ist auf der linken Seite.|  
|`HTRIGHT`|Auf der rechten Seite ist.|  
|`HTBOTTOM`|Der Punkt ist am unteren Rand.|  
|`HTBOTTOMLEFT`|Der Punkt ist unten links.|  
|`HTBOTTOMRIGHT`|Der Punkt ist unten rechts.|  
  
##  <a name="iscaptured"></a>CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdelayshow"></a>CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isrolldown"></a>CPaneFrameWnd::IsRollDown  
 Bestimmt, ob ein Minirahmenfenster abwärts zugeordnet werden soll.  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die unten Minirahmenfenster werden müssen; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework zu bestimmen, ob ein Minirahmenfenster unten ein Rollback ausgeführt werden soll. Das Rollup/Rolldownschaltfläche-Feature für ein Minirahmenfenster aktiviert ist, wenn es mindestens einen Bereich enthält, hat das `AFX_CBRS_AUTO_ROLLUP` Flag. Dieses Flag wird festgelegt, wenn ein Bereich erstellt wird. Weitere Informationen finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Standardmäßig überprüft das Framework an, ob sich der Mauszeiger befindet sich innerhalb des Minirahmenfensters Fenster umschließenden Rechtecks bestimmt, ob das Fenster unten ein Rollback ausgeführt werden. Sie können dieses Verhalten in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="isrollup"></a>CPaneFrameWnd::IsRollUp  
 Bestimmt, ob ein Minirahmenfenster aufwärts zugeordnet werden soll.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Minirahmenfenster gemacht werden muss; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework zu bestimmen, ob ein Minirahmenfenster gemacht werden soll. Das Rollup/Rolldownschaltfläche-Feature für ein Minirahmenfenster aktiviert ist, wenn es mindestens einen Bereich enthält, hat das `AFX_CBRS_AUTO_ROLLUP` Flag. Dieses Flag wird festgelegt, wenn ein Bereich erstellt wird. Weitere Informationen finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Standardmäßig überprüft das Framework an, ob sich der Mauszeiger befindet sich innerhalb des Minirahmenfensters Fenster umschließenden Rechtecks bestimmt, ob das Fenster gemacht werden. Sie können dieses Verhalten in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="killdockingtimer"></a>CPaneFrameWnd::KillDockingTimer  
 Hält den Andocktimer an.  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>CPaneFrameWnd::LoadState  
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
 Die Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand des Bereichs erfolgreich geladen wurde. andernfalls `FALSE`.  
  
##  <a name="m_busesavebits"></a>CPaneFrameWnd::m_bUseSaveBits  
 Gibt an, ob die Fensterklasse registriert, die die `CS_SAVEBITS` -Klassenstil.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses statische Element auf `TRUE` Minirahmenfensters Fensterklasse registrieren, die die `CS_SAVEBITS` Stil. Dies hilft möglicherweise verringern Flimmern, wenn ein Benutzer das Minirahmenfenster zieht.  
  
##  <a name="onbeforedock"></a>CPaneFrameWnd::OnBeforeDock  
 Bestimmt, ob Andocken möglich ist.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Andocken möglich ist. andernfalls `FALSE`.  
  
##  <a name="oncheckrollstate"></a>CPaneFrameWnd::OnCheckRollState  
 Bestimmt, ob ein Minirahmenfenster aufwärts oder abwärts zugeordnet werden soll.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework zu bestimmen, ob ein Minirahmenfenster nach oben oder unten ein Rollback ausgeführt werden soll.  
  
 Standardmäßig ruft das Framework [CPaneFrameWnd::IsRollUp](#isrollup) und [CPaneFrameWnd::IsRollDown](#isrolldown) und erstreckt, oder das Minirahmenfenster wiederhergestellt. Sie können diese Methode in einer abgeleiteten Klasse mit einem anderen visuellen Effekt überschreiben.  
  
##  <a name="ondocktorecentpos"></a>CPaneFrameWnd::OnDockToRecentPos  
 Dockt das Minirahmenfenster an der letzten Position an.  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>CPaneFrameWnd::OnDrawBorder  
 Zeichnet die Rahmen eines Minirahmenfensters.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der zum Zeichnen des Rahmens verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework zum Zeichnen der Rahmen von Minirahmenfenster aufgerufen.  
  
##  <a name="onkillrolluptimer"></a>CPaneFrameWnd::OnKillRollUpTimer  
 Hält den Rolluptimer an.  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>CPaneFrameWnd::OnMovePane  
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
  
##  <a name="onpanerecalclayout"></a>CPaneFrameWnd::OnPaneRecalcLayout  
 Passt das Layout eines Bereichs in einem Minirahmenfenster.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn das Layout eines Bereichs in das Minirahmenfenster angepasst werden muss.  
  
 Standardmäßig wird im Bereich positioniert, um den vollständigen Clientbereich des Minirahmenfenster abzudecken.  
  
##  <a name="onsetrolluptimer"></a>CPaneFrameWnd::OnSetRollUpTimer  
 Richtet den Rolluptimer ein.  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>CPaneFrameWnd::OnShowPane  
 Wird vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird.  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Der Bereich, der angezeigt oder ausgeblendet.  
  
 [in] `bShow`  
 `TRUE`Wenn der Bereich angezeigt wird; `FALSE` , wenn der Bereich ausgeblendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Wird vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="pin"></a>CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPin`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="panefrompoint"></a>CPaneFrameWnd::PaneFromPoint  
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
 `TRUE`um anzugeben, dass nur die sichtbaren Bereiche zurückgegeben werden soll; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereich, der der Benutzer geklickt hat, oder `NULL` , wenn kein Bereich an diesem Speicherort vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich zu erhalten, der den angegebenen Punkt enthält.  
  
##  <a name="redrawall"></a>CPaneFrameWnd::RedrawAll  
 Zeichnet alle Minirahmenfenster neu.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert alle Minirahmenfenster durch Aufrufen von [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) für jedes Fenster.  
  
##  <a name="removenonvalidpanes"></a>CPaneFrameWnd::RemoveNonValidPanes  
 Wird vom Framework aufgerufen, um ungültige Bereiche zu entfernen.  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>CPaneFrameWnd::RemovePane  
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
 Gibt an, was geschieht, um das Minirahmenfenster. Wenn `bDestroy` ist `TRUE`, diese Methode zerstört das Minirahmenfenster sofort. Es ist `FALSE`, diese Methode zerstört das Minirahmenfenster nach einer gewissen Verzögerung.  
  
 [in] `bNoDelayedDestroy`  
 Wenn `TRUE`, verzögert Zerstörung ist deaktiviert. Wenn `FALSE`, verzögert Zerstörung aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework kann Minirahmenfenster sofort oder nach einer gewissen Verzögerung löschen. Wenn Sie Zerstörung von Minirahmenfenster verzögern möchten, übergeben `FALSE` in der `bNoDelayedDestroy` Parameter. Verzögerte Zerstörung auftritt, wenn das Framework verarbeitet die `AFX_WM_CHECKEMPTYMINIFRAME` Nachricht.  
  
##  <a name="replacepane"></a>CPaneFrameWnd::ReplacePane  
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
  
##  <a name="savestate"></a>CPaneFrameWnd::SaveState  
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
 Die Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand des Bereichs erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
##  <a name="setcaptionbuttons"></a>CPaneFrameWnd::SetCaptionButtons  
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
  
##  <a name="setdelayshow"></a>CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelayShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdockingmanager"></a>CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pManager`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdockingtimer"></a>CPaneFrameWnd::SetDockingTimer  
 Legt den Andocktimer fest.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTimeOut`  
 Der Timeoutwert in Millisekunden.  
  
##  <a name="setdockstate"></a>CPaneFrameWnd::SetDockState  
 Legt den Andockzustand fest.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockManager`  
 Ein Zeiger auf einen andockbaren-Manager.  
  
##  <a name="sethotpoint"></a>CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptNew`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpredockstate"></a>CPaneFrameWnd::SetPreDockState  
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
 Die docking-Methode. (Dieser Parameter wird ignoriert).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Minirahmenfenster abgedockt ist. `FALSE` , wenn es angedockt ist.  
  
##  <a name="sizetocontent"></a>CPaneFrameWnd::SizeToContent  
 Passt die Größe des ein Minirahmenfenster an, damit sie einem enthaltenen Bereich entspricht.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Größe eines Minirahmenfensters auf die Größe eines enthaltenen Bereichs anpassen.  
  
##  <a name="starttearoff"></a>CPaneFrameWnd::StartTearOff  
 Schneidet ein Menü ab.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Ein Zeiger auf ein Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="storerecenttabrelatedinfo"></a>CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
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

