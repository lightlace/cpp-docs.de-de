---
title: CD2DRectU-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs: C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2bf261f31f470862a506466a8815daef796743f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cd2drectu-class"></a>CD2DRectU-Klasse
Ein Wrapper für `D2D1_RECT_U`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|Überladen. Erstellt eine `CD2DRectU` -Sitzungsobjekts `D2D1_RECT_U` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRectU::IsNull](#isnull)|Gibt eine `boolean` Wert, der angibt, ob ein Ausdruck keine gültigen Daten enthält ( `null`).|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect CD2DRectU::Operator](#operator_crect)|Konvertiert `CD2DRectU` zu `CRect` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
 Erstellt ein CD2DRectU-Objekt aus CRect-Objekt.  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Quellrechteck  
  
 `uLeft`  
 linke Koordinate der Quelle  
  
 `uTop`  
 obere Koordinate der Quelle  
  
 `uRight`  
 rechts-Koordinate Quelle  
  
 `uBottom`  
 die untere Quellkoordinate  
  
##  <a name="isnull"></a>CD2DRectU::IsNull  
 Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn nach oben, links, unteren und rechten Werte des Rechtecks alle gleich 0 sind. andernfalls "false".  
  
##  <a name="operator_crect"></a>CRect CD2DRectU::Operator  
 Konvertiert CD2DRectU in CRect-Objekt.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der D2D-Rechteck.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
