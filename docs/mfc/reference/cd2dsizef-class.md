---
title: CD2DSizeF-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f19063c29c7cbb08fadad4d55724dbbdad3ff58d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dsizef-class"></a>CD2DSizeF-Klasse
Ein Wrapper für D2D1_SIZE_F.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Überladen. Erstellt eine `CD2DSizeF` -Sitzungsobjekts `D2D1_SIZE_F` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DSizeF::IsNull](#isnull)|Gibt eine `boolean` Wert, der angibt, ob ein Ausdruck keine gültigen Daten enthält ( `null`).|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DSizeF::Operator CSize](#operator_csize)|Konvertiert `CD2DSizeF` zu `CSize` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="cd2dsizef"></a>CD2DSizeF::CD2DSizeF  
 Erstellt ein CD2DSizeF-Objekt aus CSize-Objekt.  
  
```  
CD2DSizeF(const CSize& size);  
CD2DSizeF(const D2D1_SIZE_F& size);  
  CD2DSizeF(const D2D1_SIZE_F* size);

 
CD2DSizeF(
    FLOAT cx = 0.,  
    FLOAT cy = 0.);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Größe der Datenquelle  
  
 `cx`  
 Quelle Breite  
  
 `cy`  
 Quelle Höhe  
  
##  <a name="isnull"></a>CD2DSizeF::IsNull  
 Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Breite und Höhe leer sind. andernfalls "false".  
  
##  <a name="operator_csize"></a>CD2DSizeF::Operator CSize  
 Konvertiert CD2DSizeF in CSize-Objekt.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der D2D-Größe.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
