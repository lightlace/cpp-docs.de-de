---
title: Klasse CMFCReBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
dev_langs:
- C++
helpviewer_keywords:
- CMFCReBar class
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
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
ms.openlocfilehash: 5ec432cb8cf70d31c04c718fd7e802ee9c099763
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcrebar-class"></a>CMFCReBar-Klasse
Ein `CMFCReBar` -Objekt ist eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Eine Infoleiste hinzugefügt ein Band.|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCReBar::CanFloat](#canfloat)|(Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CMFCReBar::Create](#create)|Erstellt das Grundleistensteuerelement und fügt es der `CMFCReBar` Objekt.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Überschreibt [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Bietet direkten Zugriff auf die zugrunde liegende [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Standardsteuerelements.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Überschreibt [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Überschreibt [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Überschreibt [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCReBar` Objekt kann eine Vielzahl von untergeordneten Fenstern enthalten. Dies schließt Bearbeitungsfelder, Symbolleisten und Listenfelder. Sie können die Größe der Infoleiste programmgesteuert oder des Benutzers kann manuell Infoleiste durch Ziehen der Ziehleiste. Sie können auch den Hintergrund eines Grundleisten-Objekts in eine Bitmap Ihrer Wahl festlegen.  
  
 Ein Grundleisten-Objekt verhält sich ähnlich wie ein Toolbar-Objekt. Einem Grundleisten-Steuerelement kann einen oder mehrere Bereiche enthalten, und jedes Band kann eine Ziehleiste, eine Bitmap, eine Bezeichnung und ein untergeordnetes Fenster enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCReBar` Klasse. Das Beispiel zeigt, wie einem Grundleisten-Steuerelement zu erstellen, und fügen Sie ein Band hinzu. Das Band fungiert als eine interne-Symbolleiste. Dieser Codeausschnitt ist Teil der [Rebar Probe](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest&#1;](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest&#2;](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRebar.h  
  
##  <a name="addbar"></a>CMFCReBar::AddBar  
 Eine Infoleiste hinzugefügt ein Band.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pBar`  
 Ein Zeiger auf das untergeordnete Fenster, das die Infoleiste eingefügt werden soll. Das referenzierte Objekt müssen die **WS_CHILD** Fensterstil.  
  
 [in] `pszText`  
 Gibt den Text auf die Infoleiste angezeigt werden sollen. Der Text ist nicht Teil des untergeordneten Fensters. Stattdessen wird es auf die Infoleiste selbst angezeigt.  
  
 [in] [out]`pbmp`  
 Gibt die Bitmap auf den Hintergrund des Infoleiste angezeigt werden.  
  
 [in] `dwStyle`  
 Enthält den Stil auf dem Band anwenden. Eine vollständige Liste der Band Formate finden Sie unter der Beschreibung für `fStyle` in der [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur in der Windows SDK-Dokumentation.  
  
 [in] `clrFore`  
 Die Vordergrundfarbe der Infoleiste darstellt.  
  
 [in] `clrBack`  
 Die Hintergrundfarbe der Infoleiste darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Band Infoleiste erfolgreich hinzugefügt wurde. andernfalls `FALSE`.  
  
##  <a name="create"></a>CMFCReBar::Create  
 Erstellt das Grundleistensteuerelement und fügt es der [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) Objekt.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster dieses Grundleisten-Steuerelements.  
  
 [in] `dwCtrlStyle`  
 Gibt den Stil für das Grundleistensteuerelement. Der Standardwert für die Formatvorlage ist **RBS_BANDBORDERS**, welche zeigt einschränken Zeilen um benachbarte Bänder für das Grundleistensteuerelement zu trennen. Eine Liste der gültigen Formate finden Sie unter [Grundleisten-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der Windows SDK-Dokumentation.  
  
 [in] `dwStyle`  
 Der Fensterstil des Infoleiste-Steuerelements. Eine Liste der gültigen Formate finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `nID`  
 Die Infoleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Infoleiste erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrebarctrl"></a>CMFCReBar::GetReBarCtrl  
 Bietet direkten Zugriff auf `CReBarCtrl` das zugrunde liegende Standardsteuerelement für `CMFCReBar` Objekte.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die zugrunde liegende `CReBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um Sie beim Anpassen der Infoleiste Windows Infoleiste allgemeine Funktionen von nutzen.  
  
##  <a name="calcfixedlayout"></a>CMFCReBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canfloat"></a>CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabledocking"></a>CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrebarbandinfosize"></a>CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowcontrolbarmenu"></a>CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CPoint`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontoolhittest"></a>CMFCReBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatecmdui"></a>CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanealignment"></a>CMFCReBar::SetPaneAlignment  

  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl-Klasse](../../mfc/reference/crebarctrl-class.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)

