---
title: COleResizeBar Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- OLE items, resizing
- in-place items
- in-place items, resizing
- resizing in-place OLE items
- control bars, resizing
- COleResizeBar class
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
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
ms.openlocfilehash: 99ba53c771d018b8c69c5951703b9d6f7b4afe9b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="coleresizebar-class"></a>COleResizeBar-Klasse
Ein Steuerleistentyp, die Größenanpassung von direkten OLE-Elementen unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Erstellt ein `COleResizeBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Erstellt und initialisiert ein untergeordnetes Fenster von Windows und ordnet es der `COleResizeBar` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleResizeBar`Objekte werden als ein [CRectTracker](../../mfc/reference/crecttracker-class.md) mit einem schraffierten Rahmen und äußeren vergrößern.  
  
 `COleResizeBar`-Objekte sind in der Regel eingebettete Elemente der Rahmenfensterobjekt abgeleitet der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) Klasse.  
  
 Weitere Informationen finden Sie im Artikel [Activation](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="coleresizebar"></a>COleResizeBar::COleResizeBar  
 Erstellt ein `COleResizeBar`-Objekt.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** das Resize Bar-Objekt zu erstellen.  
  
##  <a name="create"></a>COleResizeBar::Create  
 Erstellt ein untergeordnetes Fenster und ordnet sie der `COleResizeBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Balkens Größe.  
  
 `dwStyle`  
 Gibt die [Fensterstil](../../mfc/reference/window-styles.md) Attribute.  
  
 `nID`  
 Die Größe des Balkens untergeordnetes Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Größenanpassungsleiste erstellt wurde; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)

