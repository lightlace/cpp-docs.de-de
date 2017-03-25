---
title: Concurrency-Namespace Operatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 322c95da1774cb0b1d621a46c74125f435ebfbc4
ms.lasthandoff: 03/17/2017

---
# <a name="concurrency-namespace-operators"></a>Concurrency-Namespace Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[operator==](#operator_eq_eq)|[operator||](#operator_lor)|  
  
##  <a name="operator_lor"></a>Operator || Operator  
 Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.  
  
```  
template<typename ReturnType>  
task<ReturnType> operator||(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void> operator||(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `ReturnType`  
 Der Typ der zurückgegebenen Aufgabe.  
  
 `lhs`  
 Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
 `rhs`  
 Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der Eingabeaufgaben erfolgreich abgeschlossen wurde. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beide Aufgaben abgebrochen werden oder Ausnahmen auslösen, die zurückgegebene Aufgabe im abgebrochenen Zustand abgeschlossen, und eine der Ausnahmen, wenn alle auftreten, wird ausgelöst, wenn Sie aufrufen `get()` oder `wait()` für diese Aufgabe.  
  
##  <a name="operator_amp_amp"></a>Operator&amp; &amp; Operator  
 Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn beide als Argumente angegeben Aufgaben erfolgreich abgeschlossen werden.  
  
```  
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void>  operator&&(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `ReturnType`  
 Der Typ der zurückgegebenen Aufgabe.  
  
 `lhs`  
 Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
 `rhs`  
 Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn beide Eingabeaufgaben erfolgreich abgeschlossen wurden. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine der Aufgaben abgebrochen wird oder eine Ausnahme auslöst, wird die zurückgegebene Aufgabe früh im abgebrochenen Zustand abgeschlossen, und die Ausnahme, sofern sie auftritt, wird ausgelöst, wenn Sie `get()` oder `wait()` für diese Aufgabe aufrufen.  
  
##  <a name="operator_eq_eq"></a>Operator ==-Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator gleich dem `concurrent_vector`-Objekt rechts vom Operator ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn Sie der gleichzeitige Vektor auf der linken Seite des Operators gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Zwei gleichzeitige Vektoren sind gleich, wenn sie die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
##  <a name="operator_neq"></a>Operator! =-Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator ungleich dem `concurrent_vector`-Objekt rechts vom Operator ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die gleichzeitigen Vektoren nicht gleich sind. `false` , wenn die gleichzeitigen Vektoren gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Zwei gleichzeitige Vektoren sind gleich, wenn sie die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
##  <a name="operator_lt"></a>Operator&lt; Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner als das `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn Sie der gleichzeitige Vektor auf der linken Seite des Operators kleiner als der gleichzeitige Vektor auf der rechten Seite des Operators ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhalten dieses Operators ist identisch mit dem entsprechenden Operator für die `vector` -Klasse in die `std` Namespace.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
##  <a name="operator_lt_eq"></a>Operator&lt;= (Operator)  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn Sie der gleichzeitige Vektor auf der linken Seite des Operators kleiner oder gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhalten dieses Operators ist identisch mit dem entsprechenden Operator für die `vector` -Klasse in die `std` Namespace.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
##  <a name="operator_gt"></a>Operator&gt; Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator größer als das `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn Sie der gleichzeitige Vektor auf der linken Seite des Operators größer als der gleichzeitige Vektor auf der rechten Seite des Operators ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhalten dieses Operators ist identisch mit dem entsprechenden Operator für die `vector` -Klasse in die `std` Namespace.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
##  <a name="operator_gt_eq"></a>Operator&gt;= (Operator)  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator größer oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert.  
  
 `A1`  
 Der Allocator-Typ des ersten `concurrent_vector` Objekt.  
  
 `A2`  
 Der Allocator-Typ des zweiten `concurrent_vector` Objekt.  
  
 `_A`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
 `_B`  
 Ein Objekt vom Typ `concurrent_vector`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn Sie der gleichzeitige Vektor auf der linken Seite des Operators größer oder gleich dem gleichzeitigen Vektor auf der rechten Seite des Operators ist. andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhalten dieses Operators ist identisch mit dem entsprechenden Operator für die `vector` -Klasse in die `std` Namespace.  
  
 Diese Methode ist nicht parallelitätssicher ist in Bezug auf andere Methoden, die einen der gleichzeitigen Vektoren ändern könnten `_A` oder `_B`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

