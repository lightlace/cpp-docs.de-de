---
title: CD2DEllipse-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c4a801952c6b29779c381237c291232ce2ef25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dellipse-class"></a>CD2DEllipse-Klasse
Ein Wrapper für `D2D1_ELLIPSE`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Überladen. Erstellt eine `CD2DEllipse` -Sitzungsobjekts `D2D1_ELLIPSE` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse  
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
 Quellrechteck  
  
 `ellipse`  
 Quelle ellipse  
  
 `ptCenter`  
 Der Mittelpunkt der Ellipse.  
  
 `sizeRadius`  
 Die X-Radius und die Y-Achsenradius der Ellipse.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
