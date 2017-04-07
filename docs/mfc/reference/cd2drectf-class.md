---
title: CD2DRectF-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF class
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
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
ms.openlocfilehash: 5bca2dcce32679083e5917d855f711984989a489
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectf-class"></a>CD2DRectF-Klasse
Ein Wrapper für `D2D1_RECT_F`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|Überladen. Erstellt eine `CD2DRectF` -Objekt aus `D2D1_RECT_F` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|Gibt eine `boolean` -Wert, der angibt, ob ein Ausdruck keine gültigen Daten enthält ( `null`).|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectF::Operator CRect](#operator_crect)|Konvertiert `CD2DRectF` zu `CRect` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
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
 Rechteck  
  
 `fLeft`  
 linke Koordinate Source  
  
 `fTop`  
 obere Koordinate Source  
  
 `fRight`  
 rechte Koordinate Source  
  
 `fBottom`  
 die untere Koordinate Source  
  
##  <a name="isnull"></a>CD2DRectF::IsNull  
 Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn oben, links, unten und rechts Werte des Rechtecks alle gleich 0 sind. andernfalls FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectF::Operator CRect  
 Konvertiert CD2DRectF in CRect-Objekt.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktueller Wert des D2D-Rechtecks.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

