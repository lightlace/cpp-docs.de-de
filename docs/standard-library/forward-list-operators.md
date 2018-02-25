---
title: '&lt;forward_list&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
dev_langs:
- C++
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 2c56b8ccbba914b59d1a813c39db2dcc3350e822
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a> operator==  
 Testet, ob das Listenobjekt links vom Operator gleich dem Listenobjekt rechts vom Operator ist  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Vorlagenfunktion überlädt `operator==`, um zwei Objekte der Vorlagenklasse `forward_list` zu vergleichen. Die Funktion gibt `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` zurück.  
  
##  <a name="op_neq"></a> operator!=  
 Testet, ob das Listenobjekt links vom Operator ungleich dem Listenobjekt rechts vom Operator ist  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Listen ungleich sind; **FALSE**, wenn die Listen gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Vorlagenfunktion gibt `!(left == right)` zurück.  
  
##  <a name="op_lt"></a> operator&lt;  
 Testet, ob das Listenobjekt links vom Operator kleiner als das Listenobjekt auf der rechten Seite ist  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Liste links vom Operator kleiner als, aber ungleich der Liste rechts vom Operator ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Vorlagenfunktion überlädt `operator<`, um zwei Objekte der Vorlagenklasse `forward_list` zu vergleichen. Die Funktion gibt `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` zurück.  
  
##  <a name="op_lt_eq"></a> operator&lt;=  
 Testet, ob das Listenobjekt links vom Operator kleiner als oder gleich dem Listenobjekt rechts vom Operator ist  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Liste links vom Operator kleiner als oder gleich der Liste rechts des Operators ist; andernfalls `false`  
  
### <a name="remarks"></a>Hinweise  
 Diese Vorlagenfunktion gibt `!(right < left)` zurück.  
  
##  <a name="op_gt"></a> operator&gt;  
 Testet, ob das Listenobjekt links vom Operator größer als das Listenobjekt auf der rechten Seite ist  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Liste links vom Operator größer als die Liste rechts vom Operator ist; andernfalls `false`  
  
### <a name="remarks"></a>Hinweise  
 Die dritte Vorlagenfunktion gibt `right < left` zurück.  
  
##  <a name="op_gt_eq"></a> operator&gt;=  
 Testet, ob das Listenobjekt links vom Operator größer als oder gleich dem Listenobjekt rechts vom Operator ist  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Liste links vom Operator größer als oder gleich der Liste rechts vom Operator ist; andernfalls `false`  
  
### <a name="remarks"></a>Hinweise  
 Diese Vorlagenfunktion gibt `!(left < right)` zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [<forward_list>](../standard-library/forward-list.md)



