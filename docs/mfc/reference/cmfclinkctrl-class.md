---
title: CMFCLinkCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc83e5abf09102af8f27b1ee73fc78ed162b9335
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl-Klasse
Die `CMFCLinkCtrl` Klasse zeigt eine Schaltfläche als Hyperlink an und ruft das Ziel des Links auf, wenn die Schaltfläche geklickt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Zeigt eine angegebene URL als Schaltflächentext.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Legt das implizite-Protokoll (z. B. "http:") der URL.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Ändert die Größe der Schaltfläche, um den Schaltflächentext oder eine Bitmap enthalten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Vom Framework aufgerufen, bevor das Fokusrechteck der Schaltfläche gezeichnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Klicken auf eine Schaltfläche, die abgeleitet ist die `CMFCLinkCtrl` -Klasse, das Framework übergibt die URL der Schaltfläche als Parameter an die `ShellExecute` Methode. Die `ShellExecute` Methode öffnet das Ziel der URL.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Größe des eine `CMFCLinkCtrl` Objekt und Informationen zum Festlegen einer Url und QuickInfo im ein `CMFCLinkCtrl` Objekt. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 Vom Framework aufgerufen, bevor das Fokusrechteck der Schaltfläche gezeichnet wird.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectClient`  
 Ein Rechteck, das das Linksteuerelement umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie Ihren eigenen Code verwenden, auf die Schaltfläche Fokusrechteck gezeichnet werden sollen.  
  
##  <a name="seturl"></a>CMFCLinkCtrl::SetURL  
 Zeigt eine angegebene URL als Schaltflächentext.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszURL`  
 Der Schaltflächentext angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 Legt das implizite-Protokoll (z. B. "http:") der URL.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPrefix`  
 Das Präfix des URL-Protokoll.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um das URL-Präfix festzulegen. Das Präfix wird auf die Schaltfläche nicht angezeigt, aber Sie können es verwenden, um die Hilfe, um die URL-Ziel zu suchen.  
  
##  <a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 Ändert die Größe der Schaltfläche, um den Schaltflächentext oder eine Bitmap enthalten.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVCenter`  
 `TRUE`Zentrieren Sie die Schaltflächentext und Bitmap vertikal zwischen dem oberen und unteren Rand des Steuerelements Link; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
 [in] `bHCenter`  
 `TRUE`um die Schaltflächentext und Bitmap horizontal zwischen dem linken und rechten Seite des Link-Steuerelement zu zentrieren; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die neue Größe des Link-Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl-Klasse](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)
