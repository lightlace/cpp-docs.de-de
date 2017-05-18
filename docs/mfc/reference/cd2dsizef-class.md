---
title: CD2DSizeF-Klasse | Microsoft-Dokumentation
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
- CD2DSizeF class
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f780dc919f102023f2bd524fa69e73e76feec02b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsizef-class"></a>CD2DSizeF-Klasse
Ein Wrapper für D2D1_SIZE_F.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Überladen. Erstellt eine `CD2DSizeF` -Objekt aus `D2D1_SIZE_F` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DSizeF::IsNull](#isnull)|Gibt eine `boolean` -Wert, der angibt, ob ein Ausdruck keine gültigen Daten enthält ( `null`).|  
  
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
 Breite der Quelle  
  
 `cy`  
 Quelle Höhe  
  
##  <a name="isnull"></a>CD2DSizeF::IsNull  
 Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Breite und Höhe leer sind. andernfalls FALSE.  
  
##  <a name="operator_csize"></a>CD2DSizeF::Operator CSize  
 Konvertiert CD2DSizeF in CSize-Objekt.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktueller Wert der D2D-Größe.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

