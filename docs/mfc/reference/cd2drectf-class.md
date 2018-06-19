---
title: CD2DRectF-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec43e6bb14b9c5629bde60faec80d9e31e2e5188
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350796"
---
# <a name="cd2drectf-class"></a>CD2DRectF-Klasse
Ein Wrapper für `D2D1_RECT_F`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|Überladen. Erstellt eine `CD2DRectF` -Sitzungsobjekts `D2D1_RECT_F` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|Gibt eine `boolean` Wert, der angibt, ob ein Ausdruck keine gültigen Daten enthält ( `null`).|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect CD2DRectF::Operator](#operator_crect)|Konvertiert `CD2DRectF` zu `CRect` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF  
 Erstellt ein CD2DRectF-Objekt aus CRect-Objekt.  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Quellrechteck  
  
 `fLeft`  
 linke Koordinate der Quelle  
  
 `fTop`  
 obere Koordinate der Quelle  
  
 `fRight`  
 rechts-Koordinate Quelle  
  
 `fBottom`  
 die untere Quellkoordinate  
  
##  <a name="isnull"></a>  CD2DRectF::IsNull  
 Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn nach oben, links, unteren und rechten Werte des Rechtecks alle gleich 0 sind. andernfalls "false".  
  
##  <a name="operator_crect"></a>  CRect CD2DRectF::Operator  
 Konvertiert CD2DRectF in CRect-Objekt.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der D2D-Rechteck.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
