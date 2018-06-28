---
title: CMFCDropDownToolBar Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74005682036e0a4d15d17d147b5994864fa97378
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042117"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar-Klasse
Eine Symbolleiste, die angezeigt wird, wenn der Benutzer eine Symbolleisten-Schaltfläche der obersten Ebene drückt und gedrückt hält.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
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
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/571a38ab-2a56-4968-9796-273516126f80).)|  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCDropDownToolBar` Objekt kombiniert die visuelle Darstellung einer Symbolleiste mit dem Verhalten eines Popup-Menüs. Wenn ein Benutzer drückt, und enthält eine Dropdown-Symbolleisten-Schaltfläche (finden Sie unter [CMFCDropDownToolbarButton Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), wird eine Dropdown-Symbolleiste angezeigt, und der Benutzer kann aus der Dropdown-Symbolleiste eine Schaltfläche auswählen, indem Sie einen Bildlauf dorthin durchführen und Freigeben der Maus Schaltfläche ". Nachdem der Benutzer in der Dropdown-Symbolleiste eine Schaltfläche auswählt, wird diese Schaltfläche als "aktuelle"-Schaltfläche auf der Symbolleiste auf der obersten Ebene angezeigt.  
  
 Eine Dropdown-Symbolleiste kann nicht angepasst oder angedockt werden, und sie verfügt nicht über einen abtrennbare Zustand.  
  
 Die folgende Abbildung zeigt eine `CMFCDropDownToolBar` Objekt:  
  
 ![Beispiel für cmfcdropdowntoolbar](../../mfc/reference/media/cmfcdropdown.png "Cmfcdropdown")  
  
 Sie erstellen eine `CMFCDropDownToolBar` Objekt die gleiche Weise, die Sie erstellen eine gewöhnliche-Symbolleiste (finden Sie unter [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md)).  
  
 So fügen Sie einer übergeordneten Symbolleiste das Dropdown-Symbolleiste:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Erstellen einer `CMFCDropDownToolBarButton` -Objekt, das die Dropdown-Symbolleiste enthält (Weitere Informationen finden Sie unter [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).  
  
 3. Ersetzen Sie die Schaltfläche "dummy" mit der `CMFCDropDownToolBarButton` -Objekt unter Verwendung der [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen zu Symbolleisten-Schaltflächen, finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Dropdown-Symbolleiste finden Sie das Beispielprojekt VisualStudioDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode in der `CMFCDropDownToolBar` Klasse. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
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
 [in] *UiResID*  
 Die Ressourcen-ID der Bitmap, die auf die aktiven Symbolleistenbilder verweist.  
  
 [in] *UiColdResID*  
 Die Ressourcen-ID der Bitmap, die auf die inaktiven Symbolleistenbilder verweist.  
  
 [in] *UiMenuResID*  
 Die Ressourcen-ID der Bitmap, die auf die normalen Menübilder verweist.  
  
 [in] *blockiert*  
 `TRUE` auf die Symbolleiste zu sperren. andernfalls `FALSE`.  
  
 [in] *UiDisabledResID*  
 Die Ressourcen-ID der Bitmap, die auf die deaktivierten Symbolleistenbilder verweist.  
  
 [in] *UiMenuDisabledResID*  
 Die Ressourcen-ID der Bitmap, die auf die deaktivierten Menübilder verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) Methode ruft diese Methode, um die Bilder zu laden, die der Symbolleiste zugeordnet sind. Setzen Sie diese Methode außer Kraft, um die Bildressourcen benutzerdefiniert zu laden.  
  
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
 [in] *UiResID*  
 [in] *UiColdResID*  
 [in] *UiMenuResID*  
 [in] *BOOL*  
 [in] *UiDisabledResID*  
 [in] *UiMenuDisabledResID*  
 [in] *UiHotResID*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp  

  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nFlags*  
 [in] *zeigen*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove  

  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nFlags*  
 [in] *zeigen*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pButton*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pTarget*  
 [in] *bDisableIfNoHndler*  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



