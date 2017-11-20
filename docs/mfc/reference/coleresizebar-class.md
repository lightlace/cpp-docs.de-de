---
title: COleResizeBar Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs: C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3369ef30758b687c94c97e5fb0cf18bb7565ea83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[COleResizeBar::Create](#create)|Erstellt und initialisiert ein untergeordnetes Fenster von Windows und ordnet es die `COleResizeBar` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleResizeBar`Objekte werden als ein [CRectTracker](../../mfc/reference/crecttracker-class.md) mit einem schraffierten Rahmen und äußeren Handles zur Größenänderung.  
  
 `COleResizeBar`-Objekte sind in der Regel eingebettete Elemente des Rahmenfensterobjekt abgeleitet wurde. die [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) Klasse.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Rufen Sie **erstellen** Resize Bar-Objekt zu erstellen.  
  
##  <a name="create"></a>COleResizeBar::Create  
 Erstellt ein untergeordnetes Fenster, und ordnet sie der `COleResizeBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Balkens zum Ändern der Größe.  
  
 `dwStyle`  
 Gibt an, die [Fensterstil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute.  
  
 `nID`  
 Die Größe des Balkens untergeordnetes Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Größenanpassungsleiste zum Ändern der erstellt wurde; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)
