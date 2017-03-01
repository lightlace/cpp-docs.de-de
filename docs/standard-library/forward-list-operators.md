---
title: '&lt;forward_list&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a560de0a7587b5552fc663bdd2b44734a66b5f73
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
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
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
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
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a> operator&lt;  
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
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a> operator&lt;=  
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
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a> operator&gt;  
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
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a> operator&gt;=  
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




