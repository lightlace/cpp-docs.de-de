---
title: Klasse CMFCLinkCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCLinkCtrl class
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8c926c0ef611470b137d2bb897c012a85645c90c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl-Klasse
Die `CMFCLinkCtrl` Klasse eine Schaltfläche als Hyperlink angezeigt, und das Ziel des Links wird aufgerufen, wenn auf die Schaltfläche geklickt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Zeigt eine URL als Schaltflächentext an.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Legt das implizite-Protokoll (z. B. "http:") der URL.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Ändert die Größe der Schaltfläche, um den Text der Schaltfläche oder eine Bitmap enthalten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Vom Framework aufgerufen, bevor das Fokusrechteck der Schaltfläche gezeichnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie klicken Sie auf eine Schaltfläche, die von abgeleitet ist die `CMFCLinkCtrl` -Klasse, die vom Framework übergeben der URL für die Schaltfläche als Parameter an die `ShellExecute` Methode. Die `ShellExecute` Methode wird das Ziel der URL geöffnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Größe des ein `CMFCLinkCtrl` -Objekt und legen Sie eine Url und QuickInfo in ein `CMFCLinkCtrl` Objekt. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#9;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#10;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ein Rechteck, das Linksteuerelement umschließt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie Ihren eigenen Code zu verwenden, um die Schaltfläche Fokusrechteck zeichnen möchten.  
  
##  <a name="seturl"></a>CMFCLinkCtrl::SetURL  
 Zeigt eine URL als Schaltflächentext an.  
  
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
 Das Präfix eines URL-Protokoll.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um das URL-Präfix festzulegen. Das Präfix wird auf die Schaltfläche nicht angezeigt, jedoch können Sie sie auf Hilfe, um die URL-Ziel zu suchen.  
  
##  <a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 Ändert die Größe der Schaltfläche, um den Text der Schaltfläche oder eine Bitmap enthalten.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVCenter`  
 `TRUE`So zentrieren Sie die Schaltflächentext und Bitmap vertikal zwischen dem oberen und unteren Rand des Steuerelements Link; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
 [in] `bHCenter`  
 `TRUE`So zentrieren Sie die Schaltflächentext und Bitmap horizontal zwischen dem linken und rechten Rand der Link-Steuerelement; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die neue Größe des Link-Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl-Klasse](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)

