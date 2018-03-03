---
title: CMFCSpinButtonCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd6ef1957b1f4994bafa9546581e2588e33d11a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl-Klasse
Die `CMFCSpinButtonCtrl` Klasse unterstützt einen visuellen Manager, der ein Drehfeldsteuerelement zeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Standardkonstruktor|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Aktualisiert die aktuellen Drehfeld-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 Um einen visuellen Manager verwenden, um ein Drehfeld-Steuerelement in der Anwendung zu zeichnen, ersetzen Sie alle Instanzen von der `CSpinButtonCtrl` -Klasse mit der `CMFCSpinButtonCtrl` Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt von der `CMFCSpinButtonCtrl` Klasse erstellt und dessen `Create` Methode.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxspinbuttonctrl.h  
  
##  <a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 Aktualisiert die aktuellen Drehfeld-Steuerelement.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft die `CMFCSpinButtonCtrl::OnPaint` Methode zum Behandeln der [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) Nachricht, und dies wiederum Methode ruft `CMFCSpinButtonCtrl::OnDraw` Methode. Überschreiben Sie diese Methode, um die Darstellung anpassen, wie, die das Framework das Drehfeldsteuerelement zeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)
