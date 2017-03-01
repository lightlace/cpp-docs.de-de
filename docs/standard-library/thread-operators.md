---
title: '&lt;thread&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7e849e8585b372b5b423a6c960aa926ac7d5cfec
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a> operator&gt;=  
 Bestimmt, ob ein `thread::id`-Objekt größer als oder gleich einem anderen Objekt ist.  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `!(Left < Right)`  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a> operator&gt;  
 Bestimmt, ob ein `thread::id`-Objekt größer als ein anderes Objekt ist.  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `Right < Left`  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a> operator&lt;=  
 Bestimmt, ob ein `thread::id`-Objekt kleiner als oder gleich einem anderen Objekt ist.  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `!(Right < Left)`  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a> operator&lt;  
 Bestimmt, ob ein `thread::id`-Objekt kleiner als ein anderes Objekt ist.  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn `Left` `Right` in der gesamten Sortierung vorausgeht, andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator definiert eine gesamte Sortierung für alle `thread::id`-Objekte. Diese Objekte können als Schlüssel in assoziativen Containern verwendet werden.  
  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
 Überprüft zwei `thread::id`-Objekte auf Ungleichheit.  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `!(Left == Right)`  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
 Überprüft zwei `thread::id`-Objekte auf Gleichheit.  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread::id`-Objekt.  
  
 `Right`  
 Das rechte `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn beide Objekte den gleichen Ausführungsthread darstellen oder wenn kein Objekt einen Ausführungsthread darstellt, andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a> operator&lt;&lt;  
 Fügt eine Textdarstellung eines `thread::id`-Objekts in einen Stream ein.  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>Parameter  
 `Ostr`  
 Ein [basic_ostream](../standard-library/basic-ostream-class.md)-Objekt.  
  
 `Id`  
 Ein `thread::id`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `Ostr`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion fügt `Id` in `Ostr` ein.  
  
 Wenn zwei `thread::id`-Objekte gleich sind, sind die eingefügten Text-Darstellungen dieser Objekte gleich.  
  
## <a name="see-also"></a>Siehe auch  
 [\<thread>](../standard-library/thread.md)




