---
title: CTreeView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d19d4958de2f7909f2072b2ae2f59c00e63d65a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373624"
---
# <a name="ctreeview-class"></a>CTreeView-Klasse
Vereinfacht die Verwendung des Strukturansicht-Steuerelements und der [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), die Klasse, die Strukturansicht-steuerelemenfunktionalität per MFC Dokument-/ Ansichtsarchitektur kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Member  
  
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
  
##  <a name="ctreeview"></a>  CTreeView::CTreeView  
 Erstellt ein `CTreeView`-Objekt.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl  
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
