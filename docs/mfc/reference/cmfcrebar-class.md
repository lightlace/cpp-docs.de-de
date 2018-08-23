---
title: CMFCReBar-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8af155401492e97be6a9e3a80b72c8c4e7fbd9e
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538852"
---
# <a name="cmfcrebar-class"></a>CMFCReBar-Klasse
Ein `CMFCReBar` Objekt ist eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.  
   Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Eine grundleiste wird ein Band hinzugefügt.|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCReBar::CanFloat](#canfloat)|(Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CMFCReBar::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CMFCReBar` Objekt.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Überschreibt [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Bietet direkten Zugriff auf die zugrunde liegende [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Standardsteuerelements.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Überschreibt [cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Überschreibt [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Überschreibt [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCReBar` Objekt kann eine Vielzahl von untergeordneten Fenstern enthalten. Dies schließt Bearbeitungsfelder, Symbolleisten und Listenfelder. Sie können die Größe der Infoleiste programmgesteuert oder des Benutzers kann manuell grundleiste durch Ziehen der Ziehpunktleiste. Sie können auch den Hintergrund eines Grundleisten-Objekts in eine Bitmap Ihrer Wahl festlegen.  
  
 Einem Grundleisten-Objekt verhält sich ähnlich wie ein Symbolleistenobjekt. Einem Grundleisten-Steuerelement kann eine oder mehrere Bänder enthalten, und jedes Band kann eine Ziehpunktleiste, eine Bitmap, einer textbezeichnung und einem untergeordneten Fenster enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCReBar` Klasse. Das Beispiel zeigt das Erstellen eines Grundleisten-Steuerelements, und fügen Sie ein Band hinzu. Das Band fungiert als eine interne-Symbolleiste. Dieser Codeausschnitt ist Teil der [Grundleisten-Testbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRebar.h  
  
##  <a name="addbar"></a>  CMFCReBar::AddBar  
 Eine grundleiste wird ein Band hinzugefügt.  
  
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
 [in] [out] *pBar*  
 Ein Zeiger auf das untergeordnete Fenster, in die Infoleiste eingefügt werden soll. Das referenzierte Objekt müssen die **WS_CHILD** Fensterstil.  
  
 [in] *PszText*  
 Gibt den Text auf der grundleiste angezeigt werden. Der Text ist nicht Teil des untergeordneten Fensters. Stattdessen wird er auf sich selbst grundleiste angezeigt.  
  
 [in] [out] *Pbmp*  
 Gibt an, die Bitmap auf den Hintergrund der Infoleiste angezeigt werden.  
  
 [in] *DwStyle*  
 Enthält die Formatvorlage, die auf dem Band angewendet. Eine vollständige Liste der-Band-Formate, finden Sie in der Beschreibung für `fStyle` in die [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur in der Windows SDK-Dokumentation.  
  
 [in] *ClrFore*  
 Stellt die Vordergrundfarbe der Infoleiste dar.  
  
 [in] *ClrBack*  
 Stellt die Hintergrundfarbe der Infoleiste dar.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Band der Infoleiste wurde erfolgreich hinzugefügt wurde. andernfalls "false".  
  
##  <a name="create"></a>  CMFCReBar::Create  
 Erstellt das Grundleistensteuerelement, und fügt es der [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) Objekt.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] *pParentWnd*  
 Ein Zeiger auf das übergeordnete Fenster dieses Grundleisten-Steuerelements.  
  
 [in] *DwCtrlStyle*  
 Gibt den Stil für das Grundleistensteuerelement. Der Standardwert für das Format ist **RBS_BANDBORDERS**, zeigt Einschränken der Zeilen aus, um benachbarte Bänder für das Grundleistensteuerelement zu trennen. Eine Liste der gültigen Stile, finden Sie unter [Stile für Grundleisten-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der Windows SDK-Dokumentation.  
  
 [in] *DwStyle*  
 Der Fensterstil des Infoleisten-Steuerelements. Eine Liste der gültigen Stile, finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *nID*  
 Die Infoleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Infoleiste wurde erfolgreich erstellt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl  
 Bietet direkten Zugriff auf `CReBarCtrl` das zugrunde liegende allgemeine Steuerelement für `CMFCReBar` Objekte.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die zugrunde liegende `CReBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um Sie beim Anpassen Ihrer Infoleiste allgemeine Windows Grundleisten-Steuerelement-Funktionen nutzen.  
  
##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canfloat"></a>  CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwDockStyle*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CPoint*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *zeigen*  
 [in] *pTI*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pTarget*  
 [in] *bDisableIfNoHndler*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment  

  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl-Klasse](../../mfc/reference/crebarctrl-class.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)
