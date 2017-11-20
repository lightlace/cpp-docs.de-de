---
title: CTreeView-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs: C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d1d8ee7d06e9926a240ca185ce36ba0b1a180af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ctreeview-class"></a>CTreeView-Klasse
Vereinfacht die Verwendung des Strukturansicht-Steuerelements und der [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), die Klasse, die Strukturansicht-steuerelemenfunktionalität per MFC Dokument-/ Ansichtsarchitektur kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|Erstellt ein `CTreeView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|Gibt das Strukturansicht-Steuerelement mit der Ansicht verknüpfte zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu dieser Architektur, finden Sie unter der Übersicht für die [CView](../../mfc/reference/cview-class.md) Klasse und die Querverweise es sorgen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 Erstellt ein `CTreeView`-Objekt.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 Gibt einen Verweis auf die Strukturansicht-Steuerelements mit der Ansicht verknüpfte zurück.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)
