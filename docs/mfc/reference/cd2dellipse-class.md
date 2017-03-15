---
title: CD2DEllipse-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DEllipse
- CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse class
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
caps.latest.revision: 18
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
ms.openlocfilehash: c083a46e0576df7bb42fa8c4402aba320dba851c
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dellipse-class"></a>CD2DEllipse-Klasse
Ein Wrapper für `D2D1_ELLIPSE`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Überladen. Erstellt eine `CD2DEllipse` -Objekt aus `D2D1_ELLIPSE` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namecd2dellipsea--cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse  
 Erstellt ein CD2DEllipse-Objekt aus CD2DRectF-Objekt.  
  
```  
CD2DEllipse(const CD2DRectF& rect);  
CD2DEllipse(const D2D1_ELLIPSE& ellipse);  
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

 
CD2DEllipse(
    const CD2DPointF& ptCenter,  
    const CD2DSizeF& sizeRadius);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Rechteck  
  
 `ellipse`  
 Quelle ellipse  
  
 `ptCenter`  
 Der Mittelpunkt der Ellipse.  
  
 `sizeRadius`  
 Die X- und Y-Radius der Ellipse.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

