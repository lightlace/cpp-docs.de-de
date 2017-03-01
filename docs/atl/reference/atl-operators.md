---
title: ATL-Operatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: 16
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 87aadf7aacc31ded165a8e1380823cb20e614fb1
ms.lasthandoff: 02/24/2017

---
# <a name="atl-operators"></a>ATL-Operatoren
Dieser Abschnitt enthält die Themen der Referenz für die globalen ATL-Operatoren.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[Operator ==](#operator_eq_eq)|Vergleicht zwei `CSid` Objekte oder `SID` Strukturen auf Gleichheit.|  
|[Operator! =](#operator_neq)|Vergleicht zwei `CSid` Objekte oder `SID` Strukturen auf Ungleichheit.|  
|[Operator](#operator_lt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).|  
|[Operator >](#operator_gt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).|  
|[Operator<>](#operator_lt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).|  
|[Operator > =](#operator_gt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).|  
  
 Diese Operatoren sind alle in der Datei atlsecurity.h definiert.  
  
##  <a name="a-nameoperatoreqeqa--operator-"></a><a name="operator_eq_eq"></a>Operator ==  
 Vergleicht `CSid` Objekte oder `SID` (Security Identifier) Strukturen auf Gleichheit.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn die Objekte gleich sind, **false** , wenn sie nicht gleich sind.  
  
##  <a name="a-nameoperatorneqa--operator-"></a><a name="operator_neq"></a>Operator! =  
 Vergleicht `CSid` Objekte oder `SID` (Security Identifier) Strukturen auf Ungleichheit.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn die Objekte nicht gleich sind, **false** Wenn sie gleich sind.  
  
##  <a name="a-nameoperatorlta--operator-"></a><a name="operator_lt"></a>Operator  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn die Adresse der `lhs` Objekt ist kleiner als die Adresse des der `rhs` -Objekt, **false** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur, und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="a-nameoperatorgta--operator-"></a><a name="operator_gt"></a>Operator >  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn die Adresse der `lhs` ist größer als die Adresse der `rhs`, **false** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur, und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="a-nameoperatorlteqa--operator-"></a><a name="operator_lt__eq"></a>Operator<=></=>  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn die Adresse der `lhs` ist kleiner oder gleich der Adresse der `rhs`, **false** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur, und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.  
  
##  <a name="a-nameoperatorgteqa--operator-"></a><a name="operator_gt__eq"></a>Operator > =  
 Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für die Kompatibilität der C++-Standardbibliothek).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
 `rhs`  
 Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn die Adresse der `lhs` ist größer als oder gleich auf die Adresse der `rhs`, **false** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` Struktur, und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek Auflistungsklassen bereitzustellen.




