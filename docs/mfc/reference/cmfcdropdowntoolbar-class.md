---
title: CMFCDropDownToolBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar class
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ba643d67b12ba22bcf9fb54d32f3c329fa2c65a0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar-Klasse
Eine Symbolleiste, die angezeigt wird, wenn der Benutzer eine Symbolleisten-Schaltfläche der obersten Ebene drückt und gedrückt hält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Mitglieder  
  
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
 Ein `CMFCDropDownToolBar` -Objekt kombiniert die visuelle Darstellung einer Symbolleiste mit dem Verhalten von ein Popup-Menü. Wenn ein Benutzer drückt und enthält eine Dropdown-Symbolleisten-Schaltfläche (finden Sie unter [CMFCDropDownToolbarButton Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), wird eine Dropdown-Symbolleiste angezeigt, und der Benutzer kann aus der Dropdown-Symbolleiste eine Schaltfläche auswählen, indem Sie einen Bildlauf dorthin durchführen und die Maustaste loslassen. Nachdem der Benutzer in der Dropdown-Symbolleiste eine Schaltfläche auswählt, wird die Schaltfläche als die aktuelle Schaltfläche auf der Symbolleiste auf der obersten Ebene angezeigt.  
  
 Eine Dropdown-Symbolleiste kann nicht angepasst oder angedockt und hat keinen abtrennbare Zustand.  
  
 Die folgende Abbildung zeigt ein `CMFCDropDownToolBar` Objekt:  
  
 ![Beispiel für cmfcdropdowntoolbar](../../mfc/reference/media/cmfcdropdown.png "Cmfcdropdown")  
  
 Sie erstellen eine `CMFCDropDownToolBar` -Objekt die gleiche Weise, die Sie erstellen eine normale Symbolleiste (finden Sie unter [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md)).  
  
 Um die Dropdown-Symbolleiste in einer übergeordneten Symbolleiste einzufügen:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Erstellen einer `CMFCDropDownToolBarButton` -Objekt, das die Dropdown-Symbolleiste enthält (Weitere Informationen finden Sie unter [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).  
  
 3. Ersetzen Sie die platzhalterschaltfläche mit der `CMFCDropDownToolBarButton` Objekt mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen zu Symbolleisten-Schaltflächen, finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Dropdown-Symbolleiste finden Sie das Beispielprojekt VisualStudioDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der `CMFCDropDownToolBar` Klasse. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#29;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#30;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
##  <a name="a-nameallowshowonpanemenua--cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCDropDownToolBar::AllowShowOnPaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameloadbitmapa--cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>CMFCDropDownToolBar::LoadBitmap  
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
 [in] `uiResID`  
 Die Ressourcen-ID der Bitmap, die auf die aktiven Symbolleistenbilder verweist.  
  
 [in] `uiColdResID`  
 Die Ressourcen-ID der Bitmap, die auf die inaktiven Symbolleistenbilder verweist.  
  
 [in] `uiMenuResID`  
 Die Ressourcen-ID der Bitmap, die auf die normalen Menübilder verweist.  
  
 [in] `bLocked`  
 `TRUE`auf die Symbolleiste zu sperren. andernfalls `FALSE`.  
  
 [in] `uiDisabledResID`  
 Die Ressourcen-ID der Bitmap, die auf die deaktivierten Symbolleistenbilder verweist.  
  
 [in] `uiMenuDisabledResID`  
 Die Ressourcen-ID der Bitmap, die auf die deaktivierten Menübilder verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) -Methode ruft diese Methode, um die Bilder zu laden, die der Symbolleiste zugeordnet sind. Setzen Sie diese Methode außer Kraft, um die Bildressourcen benutzerdefiniert zu laden.  
  
 Rufen Sie die `LoadBitmapEx` -Methode auf, um nach der Erstellung der Symbolleiste weitere Bilder zu laden.  
  
##  <a name="a-nameloadtoolbara--cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CMFCDropDownToolBar::LoadToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [in] `uiResID`  
 [in] `uiColdResID`  
 [in] `uiMenuResID`  
 [in] `BOOL`  
 [in] `uiDisabledResID`  
 [in] `uiMenuDisabledResID`  
 [in] `uiHotResID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttonupa--cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>CMFCDropDownToolBar::OnLButtonUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 [in] `point`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonmousemovea--cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>CMFCDropDownToolBar::OnMouseMove  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlags`  
 [in] `point`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsendcommanda--cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>CMFCDropDownToolBar::OnSendCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdatecmduia--cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCDropDownToolBar::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




