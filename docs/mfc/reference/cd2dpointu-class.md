---
title: CD2DPointU-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91496e96763ab8c79ae1c71d68b9ae8f8db15e50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dpointu-class"></a>CD2DPointU-Klasse
Ein Wrapper für `D2D1_POINT_2U`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Überladen. Erstellt eine `CD2DPointU` vom Objekt `D2D1_POINT_2U` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPointU::Operator CPoint](#operator_cpoint)|Konvertiert `CD2DPointU` zu `CPoint` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU  
 Erstellt ein CD2DPointU-Objekt aus CPoint-Objekt.  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Dienstpunkt an.  
  
 `uX`  
 Quelle X  
  
 `uY`  
 Quelle Y  
  
##  <a name="operator_cpoint"></a>  CD2DPointU::Operator CPoint  
 Konvertiert CD2DPointU in CPoint-Objekt.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der D2D-Punkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
