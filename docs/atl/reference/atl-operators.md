---
title: ATL-Operatoren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75c9ffb8c918cce70ad1e150dd80cb07ebdd7b34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="atl-operators"></a>ATL-Operatoren
Dieser Abschnitt enthält die Referenzthemen für die globalen ATL-Operatoren.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[operator ==](#operator_eq_eq)|Vergleicht zwei `CSid` Objekte oder `SID` Strukturen auf Gleichheit.|  
|[Operator! =](#operator_neq)|Vergleicht zwei `CSid` Objekte oder `SID` Strukturen auf Ungleichheit.|  
|[Operator <](#operator_lt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als das `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).|  
|[operator >](#operator_gt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).|  
|[operator <=](#operator_lt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).|  
|[operator >=](#operator_gt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h.  
  
##  <a name="operator_eq_eq"></a>  Operator ==  
 Vergleicht `CSid` Objekte oder `SID` (Sicherheits-ID) Strukturen auf Gleichheit.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Objekte gleich sind, **"false"** Wenn sie nicht gleich sind.  
  
##  <a name="operator_neq"></a>  Operator! =  
 Vergleicht `CSid` Objekte oder `SID` (Sicherheits-ID) Strukturen auf Ungleichheit.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Objekte nicht gleich sind, **"false"** bei vorliegender.  
  
##  <a name="operator_lt"></a>  Operator <  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als das `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die Adresse des dem `lhs` -Objekts kleiner ist als die Adresse des der `rhs` Objekt **"false"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur und wird implementiert, um Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="operator_gt"></a>  Operator >  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die Adresse der `lhs` ist größer als die Adresse des der `rhs`, **"false"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur und wird implementiert, um Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="operator_lt__eq"></a>  Operator < =  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die Adresse des der `lhs` ist kleiner oder gleich der Adresse der `rhs`, **"false"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur und wird implementiert, um Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="operator_gt__eq"></a>  Operator > =  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (C++-Standardbibliothek Kompatibilitätsgründen).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` Struktur zu vergleichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die Adresse des dem `lhs` ist größer als oder gleich der Adresse des dem `rhs`, **"false"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur und wird implementiert, um Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.



