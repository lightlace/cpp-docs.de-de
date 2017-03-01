---
title: CListView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- CListView class
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
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
ms.openlocfilehash: ebf6c93aa6d88d1942af4ecb9e3373fa57d84b65
ms.lasthandoff: 02/24/2017

---
# <a name="clistview-class"></a>CListView-Klasse
Vereinfacht die Verwendung des Steuerelements und der [CListCtrl](../../mfc/reference/clistctrl-class.md), Klasse, die Listensteuerelement-Funktionalität, mit der MFC-Dokument-/ Ansichtarchitektur kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Erstellt ein `CListView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Das mit der Ansicht verknüpfte Listensteuerelement zurück.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Entfernt die angegebene Liste in der Listenansicht angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu dieser Architektur, finden Sie unter Übersicht über die für die [CView](../../mfc/reference/cview-class.md) -Klasse und die Querverweise genannten vorhanden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcview.h  
  
##  <a name="a-nameclistviewa--clistviewclistview"></a><a name="clistview"></a>CListView::CListView  
 Erstellt ein `CListView`-Objekt.  
  
```  
CListView();
```  
  
##  <a name="a-namegetlistctrla--clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView::GetListCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Verweises auf das Listensteuerelement, das der Ansicht zugeordnet.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Listensteuerelement, das der Ansicht zugeordnet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView&#7;](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="a-nameremoveimagelista--clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::RemoveImageList  
 Entfernt die angegebene Liste in der Listenansicht angezeigt.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `nImageList`  
 Der nullbasierte Index des Bilds zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel ROWLIST](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)

