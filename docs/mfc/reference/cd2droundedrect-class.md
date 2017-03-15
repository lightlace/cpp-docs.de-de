---
title: CD2DRoundedRect-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DRoundedRect
- CD2DRoundedRect
dev_langs:
- C++
helpviewer_keywords:
- CD2DRoundedRect class
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
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
ms.openlocfilehash: f9522f8555c37cd4a15b425c36cfa2d1b1b9851c
ms.lasthandoff: 02/24/2017

---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect-Klasse
Ein Wrapper für `D2D1_ROUNDED_RECT`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Überladen. Erstellt eine `CD2DRoundedRect` -Objekt aus `D2D1_ROUNDED_RECT` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_ROUNDED_RECT`  
  
 [CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namecd2droundedrecta--cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a>CD2DRoundedRect::CD2DRoundedRect  
 Erstellt ein CD2DRoundedRect-Objekt aus CD2DRectF-Objekt.  
  
```  
CD2DRoundedRect(
    const CD2DRectF& rectIn,  
    const CD2DSizeF& sizeRadius);  
  
CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);  
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```  
  
### <a name="parameters"></a>Parameter  
 `rectIn`  
 Rechteck  
  
 `sizeRadius`  
 RADIUS-Größe  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

