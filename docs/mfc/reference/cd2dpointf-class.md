---
title: CD2DPointF-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b369be53d14af49eb112026089226214f0d7d73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dpointf-class"></a>CD2DPointF-Klasse
Ein Wrapper für `D2D1_POINT_2F`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Überladen. Erstellt eine `CD2DPointF` -Sitzungsobjekts `D2D1_POINT_2F` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPointF::Operator CPoint](#operator_cpoint)|Konvertiert `CD2DPointF` zu `CPoint` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>CD2DPointF::CD2DPointF  
 Erstellt ein CD2DPointF-Objekt aus CPoint-Objekt.  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Dienstpunkt an.  
  
 `fX`  
 Quelle X  
  
 `fY`  
 Quelle Y  
  
##  <a name="operator_cpoint"></a>CD2DPointF::Operator CPoint  
 Konvertiert CD2DPointF in CPoint-Objekt.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der D2D-Punkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
