---
title: CListView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs:
- C++
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9087642a529911c0c0a885c4613a3dbf2e92311f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037614"
---
# <a name="clistview-class"></a>CListView-Klasse
Vereinfacht die Verwendung des Listensteuerelements und von [CListCtrl](../../mfc/reference/clistctrl-class.md), die Klasse, die Listensteuerelement-Funktionalität, mit der MFC-Dokument-/ Ansichtsarchitektur kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Erstellt ein `CListView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Gibt das Strukturelement-Steuerelement mit der Ansicht verknüpfte zurück.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Entfernt die angegebenen Bildliste in der Listenansicht angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu dieser Architektur, finden Sie unter der Übersicht für die [CView](../../mfc/reference/cview-class.md) Klasse und die Querverweise es sorgen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcview.h  
  
##  <a name="clistview"></a>  CListView::CListView  
 Erstellt ein `CListView`-Objekt.  
  
```  
CListView();
```  
  
##  <a name="getlistctrl"></a>  CListView::GetListCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Verweises auf das Strukturelement-Steuerelement, das der Ansicht zugeordnet.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Strukturelement-Steuerelement, das der Ansicht zugeordnet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="removeimagelist"></a>  CListView::RemoveImageList  
 Entfernt die angegebenen Bildliste in der Listenansicht angezeigt.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *nImageList*  
 Der nullbasierte Index des Bilds zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel ROWLIST](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)
