---
title: Concurrency-Namespace Operatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 7fc7b500d882bb4e023904a147a7736996b5c5de
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators"></a>Concurrency-Namespace Operatoren
||||  
|-|-|-|  
|[Operator! =-Operator](#operator_neq)|[Operator&amp; &amp; Operator](#operator_amp_amp)|[Operator&gt; Operator](#operator_gt)|  
|[Operator&gt;= (Operator)](#operator_gt_eq)|[Operator&lt; Operator](#operator_lt)|[Operator&lt;= (Operator)](#operator_lt_eq)|  
|[Operator ==-Operator](#operator_eq_eq)|[operator|| Operator](#operator_lor)|  
  
##  <a name="a-nameoperatorlora--operator124124-operator"></a><a name="operator_lor"></a>Operator || Operator  
 Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.  
  
```  
template<
    typename _ReturnType  
>  
task<_ReturnType>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>   operator||(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `_ReturnType`  
 Der Typ der zurückgegebenen Aufgabe.  
  
 `_Lhs`  
 Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
 `_Rhs`  
 Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der Eingabeaufgaben erfolgreich abgeschlossen wurde. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beide Aufgaben abgebrochen werden oder Ausnahmen auslösen, die zurückgegebene Aufgabe im abgebrochenen Zustand abgeschlossen, und eine der Ausnahmen, wenn alle auftreten, wird ausgelöst, wenn Sie aufrufen `get()` oder `wait()` für diese Aufgabe.  
  
##  <a name="a-nameoperatorampampa--operatorampamp-operator"></a><a name="operator_amp_amp"></a>Operator&amp; &amp; Operator  
 Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn beide als Argumente angegeben Aufgaben erfolgreich abgeschlossen werden.  
  
```  
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>    operator&&(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `_ReturnType`  
 Der Typ der zurückgegebenen Aufgabe.  
  
 `_Lhs`  
 Die erste Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
 `_Rhs`  
 Die zweite Aufgabe, die mit der resultierenden Aufgabe kombiniert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn beide Eingabeaufgaben erfolgreich abgeschlossen wurden. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine der Aufgaben abgebrochen wird oder eine Ausnahme auslöst, wird die zurückgegebene Aufgabe früh im abgebrochenen Zustand abgeschlossen, und die Ausnahme, sofern sie auftritt, wird ausgelöst, wenn Sie `get()` oder `wait()` für diese Aufgabe aufrufen.  
  
##  <a name="a-nameoperatoreqeqa--operator-operator"></a><a name="operator_eq_eq"></a>Operator ==-Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator gleich dem `concurrent_vector`-Objekt rechts vom Operator ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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
  
##  <a name="a-nameoperatorneqa--operator-operator"></a><a name="operator_neq"></a>Operator! =-Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator ungleich dem `concurrent_vector`-Objekt rechts vom Operator ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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
  
##  <a name="a-nameoperatorlta--operatorlt-operator"></a><a name="operator_lt"></a>Operator&lt; Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner als das `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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
  
##  <a name="a-nameoperatorlteqa--operatorlt-operator"></a><a name="operator_lt_eq"></a>Operator&lt;= (Operator)  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator kleiner oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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
  
##  <a name="a-nameoperatorgta--operatorgt-operator"></a><a name="operator_gt"></a>Operator&gt; Operator  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator größer als das `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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
  
##  <a name="a-nameoperatorgteqa--operatorgt-operator"></a><a name="operator_gt_eq"></a>Operator&gt;= (Operator)  
 Testet, ob das `concurrent_vector`-Objekt links vom Operator größer oder gleich dem `concurrent_vector`-Objekt auf der rechten Seite ist.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
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

