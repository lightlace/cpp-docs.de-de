---
title: '&lt;atomic&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_compare_exchange_strong
- atomic/std::atomic_compare_exchange_strong_explicit
- atomic/std::atomic_compare_exchange_weak
- atomic/std::atomic_compare_exchange_weak_explicit
- atomic/std::atomic_exchange
- atomic/std::atomic_exchange_explicit
- atomic/std::atomic_fetch_add
- atomic/std::atomic_fetch_add_explicit
- atomic/std::atomic_fetch_and
- atomic/std::atomic_fetch_and_explicit
- atomic/std::atomic_fetch_or
- atomic/std::atomic_fetch_or_explicit
- atomic/std::atomic_fetch_sub
- atomic/std::atomic_fetch_sub_explicit
- atomic/std::atomic_fetch_xor
- atomic/std::atomic_fetch_xor_explicit
- atomic/std::atomic_flag_clear
- atomic/std::atomic_flag_clear_explicit
- atomic/std::atomic_flag_test_and_set
- atomic/std::atomic_flag_test_and_set_explicit
- atomic/std::atomic_init
- atomic/std::atomic_is_lock_free
- atomic/std::atomic_load
- atomic/std::atomic_load_explicit
- atomic/std::atomic_signal_fence
- atomic/std::atomic_store
- atomic/std::atomic_store_explicit
- atomic/std::atomic_thread_fence
- atomic/std::kill_dependency
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9915c89415594b1cc3475a458ec3a1fbdcfdf290
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="ltatomicgt-functions"></a>&lt;atomic&gt;-Funktionen
||||  
|-|-|-|  
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak)|  
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit)|[atomic_exchange](#atomic_exchange)|[atomic_exchange_explicit](#atomic_exchange_explicit)|  
|[atomic_fetch_add](#atomic_fetch_add)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit)|[atomic_fetch_and](#atomic_fetch_and)|  
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit)|[atomic_fetch_or](#atomic_fetch_or)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit)|  
|[atomic_fetch_sub](#atomic_fetch_sub)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit)|[atomic_fetch_xor](#atomic_fetch_xor)|  
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit)|[atomic_flag_clear](#atomic_flag_clear)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit)|  
|[atomic_flag_test_and_set](#atomic_flag_test_and_set)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit)|[atomic_init](#atomic_init)|  
|[atomic_is_lock_free](#atomic_is_lock_free)|[atomic_load](#atomic_load)|[atomic_load_explicit](#atomic_load_explicit)|  
|[atomic_signal_fence](#atomic_signal_fence)|[atomic_store](#atomic_store)|[atomic_store_explicit](#atomic_store_explicit)|  
|[atomic_thread_fence](#atomic_thread_fence)|[kill_dependency](#kill_dependency)|  
  
##  <a name="atomic_compare_exchange_strong"></a> atomic_compare_exchange_strong  
 Führt einen atomischen Vergleichs- und Austausch-Vorgang aus.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Exp`  
 Ein Zeiger auf einen Wert des Typs `Ty`.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein das Ergebnis des Wertevergleichs angebendes `bool`-Element.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode wird ein atomischer Vergleichs- und Austauschvorgang ausgeführt, indem implizite `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argumente verwendet werden. Weitere Informationen finden Sie unter [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).  
  
##  <a name="atomic_compare_exchange_strong_explicit"></a> atomic_compare_exchange_strong_explicit  
 Führt einen *atomischen Vergleichs- und Austauschvorgang* aus.  
  
```
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Exp`  
 Ein Zeiger auf einen Wert des Typs `Ty`.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
 `Order1`  
 Erstes [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argument.  
  
 `Order2`  
 Zweites `memory_order`-Argument. Der Wert von `Order2` kann nicht `memory_order_release` oder `memory_order_acq_rel` sein, er kann nicht stärker als der Wert von `Order1` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein das Ergebnis des Wertevergleichs angebendes `bool`-Element.  
  
### <a name="remarks"></a>Hinweise  
 Mit einem *atomischen Vergleichs- und Austauschvorgang* wird der Wert verglichen, der in dem Objekt gespeichert wird, auf das von `Atom` gegen den Wert gezeigt wird, auf den von `Exp` gezeigt wird. Wenn die Werte gleich sind, wird der Wert, der in dem Objekt gespeichert wird, auf das von `atom` gezeigt wird, durch `Val` ersetzt, indem ein `read-modify-write`-Vorgang verwendet und die von `Order1` angegebenen Einschränkungen für die Speicherreihenfolge angewendet werden. Wenn die Werte nicht gleich sind, wird der Wert, auf den von `Exp` mit dem Wert ersetzt, der in dem Objekt gespeichert ist, auf das von `Atom` gezeigt wird, und es werden die von `Order2` angegebenen Einschränkungen für die Arbeitsspeicherreihenfolge angewendet.  
  
##  <a name="atomic_compare_exchange_weak"></a> atomic_compare_exchange_weak  
 Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Exp`  
 Ein Zeiger auf einen Wert des Typs `Ty`.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein das Ergebnis des Wertevergleichs angebendes `bool`-Element.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode wird ein *schwacher atomischer Vergleichs- und Austauschvorgang* ausgeführt, der über implizite `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argumente verfügt. Weitere Informationen finden Sie unter [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).  
  
##  <a name="atomic_compare_exchange_weak_explicit"></a> atomic_compare_exchange_weak_explicit  
 Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp, 
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Exp`  
 Ein Zeiger auf einen Wert des Typs `Ty`.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
 `Order1`  
 Erstes [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argument.  
  
 `Order2`  
 Zweites `memory_order`-Argument. Der Wert von `Order2` kann weder `memory_order_release` oder `memory_order_acq_rel` sein, noch kann er stärker als der Wert von `Order1` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein das Ergebnis des Wertevergleichs angebendes `bool`-Element.  
  
### <a name="remarks"></a>Hinweise  
 Mit einem *atomischen Vergleichs- und Austauschvorgang* wird der Wert verglichen, der in dem Objekt gespeichert wird, auf das von `Atom` mit dem Wert gezeigt wird, auf den von `Exp` gezeigt wird. Wenn die Werte gleich sind, wird mit dem Vorgang der Wert, der in dem Objekt gespeichert wird, auf das von `Atom` gezeigt wird, durch `Val` ersetzt, indem ein `read-modify-write`-Vorgang verwendet und die von `Order1` angegebenen Einschränkungen für die Arbeitsspeicherreihenfolge angewendet werden. Wenn die Werte nicht gleich sind, wird der Wert, auf den von `Exp` mit dem Wert ersetzt, der in dem Objekt gespeichert ist, auf das von `Atom` gezeigt wird, und es werden die von `Order2` angegebenen Einschränkungen für die Arbeitsspeicherreihenfolge angewendet.  
  
 Mit einem *schwachen* atomischen Vergleichs- und Austauschvorgang wird ein Austausch ausgeführt, wenn die verglichenen Werte gleich sind. Wenn die Werte allerdings nicht gleich sind, ist nicht sichergestellt, dass Austausch mit dem Vorgang ausgeführt wird.  
  
##  <a name="atomic_exchange"></a> atomic_exchange  
 Verwendet `Value`, um den gespeicherten Wert von `Atom` zu ersetzen.  
  
```
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der gespeicherte Wert von `Atom` vor dem Austausch.  
  
### <a name="remarks"></a>Hinweise  
 Die `atomic_exchange`-Funktion führt einen `read-modify-write`-Vorgang aus, um den in `Atom` gespeicherten Wert mithilfe von `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) mit `Value` auszutauschen.  
  
##  <a name="atomic_exchange_explicit"></a> atomic_exchange_explicit  
 Ersetzt den gespeicherten Wert von `Atom` durch `Value`.  
  
```
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der gespeicherte Wert von `Atom` vor dem Austausch.  
  
### <a name="remarks"></a>Hinweise  
 Die `atomic_exchange_explicit`-Funktion führt einen `read-modify-write`-Vorgang aus, um den in `Atom` gespeicherten Wert mit `Value` innerhalb der von `Order` angegebenen Speicherplatzeinschränkungen auszutauschen.  
  
##  <a name="atomic_fetch_add"></a> atomic_fetch_add  
 Fügt einem vorhandenen Wert einen in einem `atomic`-Objekt gespeicherten Wert hinzu.  
  
```
template <class T>  
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>  
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Zeiger auf den Typ `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `ptrdiff_t`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion `atomic_fetch_add` führt einen `read-modify-write`-Vorgang aus, um dem in `Atom` gespeicherten Wert atomisch `Value` hinzuzufügen, indem die `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkung verwendet wird.  
  
 Wenn der atomische Typ `atomic_address` ist, dann ist `Value` vom Typ `ptrdiff_t`, und der Vorgang behandelt den gespeicherten Zeiger als `char *`.  
  
 Dieser Vorgang wird auch bei Integraltypen überladen:  
  
```
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="atomic_fetch_add_explicit"></a> atomic_fetch_add_explicit  
 Fügt einem vorhandenen Wert einen in einem `atomic`-Objekt gespeicherten Wert hinzu.  
  
```
template <class T>  
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom, 
    ptrdiff_t Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Zeiger auf den Typ `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `ptrdiff_t`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Die `atomic_fetch_add_explicit`-Funktion führt einen `read-modify-write`-Vorgang aus, um `Value` atomisch dem in `Atom` gespeicherten Wert innerhalb der von `Order` angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen hinzuzufügen.  
  
 Wenn der atomische Typ `atomic_address` ist, dann ist `Value` vom Typ `ptrdiff_t`, und der Vorgang behandelt den gespeicherten Zeiger als `char *`.  
  
 Dieser Vorgang wird auch bei Integraltypen überladen:  
  
```cpp  
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="atomic_fetch_and"></a> atomic_fetch_and  
 Führt ein bitweises `and` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_and`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, um den gespeicherten Wert von `Atom` durch ein bitweises `and` von `Value` und den aktuellen in `Atom` gespeicherten Wert unter Verwendung der `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkung zu ersetzen.  
  
##  <a name="atomic_fetch_and_explicit"></a> atomic_fetch_and_explicit  
 Führt ein bitweises `and` eines Werts und einen vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
    
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_and_explicit`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, bei dem der gespeicherte Wert von `Atom` mit einem bitweisen `and` von `Value` und dem aktuellen in `Atom` gespeicherten Wert ersetzt wird, der innerhalb der von `Order` angegeben Arbeitsspeichereinschränkungen gespeichert wird.  
  
##  <a name="atomic_fetch_or"></a> atomic_fetch_or  
 Führt ein bitweises `or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_or`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, um den gespeicherten Wert von `Atom` durch ein bitweises `or` von `Value` und den aktuellen in `Atom` gespeicherten Wert unter Verwendung von `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) zu ersetzen.  
  
##  <a name="atomic_fetch_or_explicit"></a> atomic_fetch_or_explicit  
 Führt ein bitweises `or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_or_explicit`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, bei dem der gespeicherte Wert von `Atom` durch einen bitweisen `or` von `Value` und den aktuellen in `Atom` gespeicherten Wert ersetzt wird, der innerhalb der von `Order` angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen gespeichert wird.  
  
##  <a name="atomic_fetch_sub"></a> atomic_fetch_sub  
 Subtrahiert einen Wert von einem in einem `atomic`-Objekt vorhandenen Wert.  
  
```
template <class T>  
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>  
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Zeiger auf den Typ `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `ptrdiff_t`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Die `atomic_fetch_sub`-Funktion führt einen `read-modify-write`-Vorgang aus, um `Value` mithilfe der `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkung atomisch vom gespeicherten Wert in `Atom` zu subtrahieren.  
  
 Wenn der atomische Typ `atomic_address` ist, dann ist `Value` vom Typ `ptrdiff_t`, und der Vorgang behandelt den gespeicherten Zeiger als `char *`.  
  
 Dieser Vorgang wird auch bei Integraltypen überladen:  
  
```
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="atomic_fetch_sub_explicit"></a> atomic_fetch_sub_explicit  
 Subtrahiert einen Wert von einem in einem `atomic`-Objekt vorhandenen Wert.  
  
```
template <class T>  
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Zeiger auf den Typ `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `ptrdiff_t`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Die `atomic_fetch_sub_explicit`-Funktion führt einen `read-modify-write`-Vorgang aus, um `Value` atomisch vom in `Atom` gespeicherten Wert innerhalb der von `Order` angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen zu subtrahieren.  
  
 Wenn der atomische Typ `atomic_address` ist, dann ist `Value` vom Typ `ptrdiff_t`, und der Vorgang behandelt den gespeicherten Zeiger als `char *`.  
  
 Dieser Vorgang wird auch bei Integraltypen überladen:  
  
```cpp  
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="atomic_fetch_xor"></a> atomic_fetch_xor  
 Führt ein bitweises `exclusive or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept; 

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_xor`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, um den gespeicherten Wert von `Atom` durch ein bitweises `exclusive or` von `Value` und den aktuellen in `Atom` gespeicherten Wert unter Verwendung von `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) zu ersetzen.  
  
##  <a name="atomic_fetch_xor_explicit"></a> atomic_fetch_xor_explicit  
 Führt ein bitweises `exclusive or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.  
  
```
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `T`.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.  
  
### <a name="remarks"></a>Hinweise  
 Mit der `atomic_fetch_xor_explicit`-Funktion wird ein `read-modify-write`-Vorgang ausgeführt, bei dem der gespeicherte Wert von `Atom` durch einen bitweisen `exclusive or` von `Value` und den aktuellen in `Atom` gespeicherten Wert ersetzt wird, der innerhalb der von `Order` angegeben [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen gespeichert wird.  
  
##  <a name="atomic_flag_clear"></a> atomic_flag_clear  
 Legt das `bool`-Flag in einem [atomic_flag](../standard-library/atomic-flag-structure.md)-Objekt innerhalb von `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) auf `false` fest.  
  
```
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Flag`  
 Ein Zeiger auf ein `atomic_flag`-Objekt.  
  
##  <a name="atomic_flag_clear_explicit"></a> atomic_flag_clear_explicit  
 Legt das `bool`-Flag in einem [atomic_flag](../standard-library/atomic-flag-structure.md)-Objekt innerhalb der angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen auf `false` fest.  
  
```
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Flag`  
 Ein Zeiger auf ein `atomic_flag`-Objekt.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_flag_test_and_set"></a> atomic_flag_test_and_set  
 Legt das `bool`-Flag in einem [atomic_flag](../standard-library/atomic-flag-structure.md)-Objekt innerhalb der Einschränkungen von `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) auf `true` fest.  
  
```
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Flag`  
 Ein Zeiger auf ein `atomic_flag`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Anfangswert von `Flag`.  
  
##  <a name="atomic_flag_test_and_set_explicit"></a> atomic_flag_test_and_set_explicit  
 Legt das `bool`-Flag in einem [atomic_flag](../standard-library/atomic-flag-structure.md)-Objekt innerhalb der angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen auf `true` fest.  
  
```
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Flag`  
 Ein Zeiger auf ein `atomic_flag`-Objekt.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Anfangswert von `Flag`.  
  
##  <a name="atomic_init"></a> atomic_init  
 Legt den gespeicherten Wert in einem `atomic`-Objekt fest.  
  
```
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` gespeichert wird.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="remarks"></a>Hinweise  
 `atomic_init` ist kein atomischer Vorgang. Ist nicht threadsicher.  
  
##  <a name="atomic_is_lock_free"></a> atomic_is_lock_free  
 Gibt an, ob die atomischen Vorgänge auf ein `atomic`-Objekt *sperrfrei* sind.  
  
```
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `T` gespeichert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn atomische Vorgänge auf `Atom` sperrfrei sind; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Ein atomischer Typ ist sperrfrei, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden. Wenn diese Funktion TRUE zurückgibt, ist der Typ sicher und kann in Signalhandlern verwendet werden.  
  
##  <a name="atomic_load"></a> atomic_load  
 Ruft den gespeicherten Wert in einem `atomic`-Objekt ab.  
  
```
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` enthalten ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der abgerufene Wert, der in `Atom`-gespeichert wird.  
  
### <a name="remarks"></a>Hinweise  
 `atomic_load` verwendet implizit `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_load_explicit"></a> atomic_load_explicit  
 Ruft den gespeicherten Wert in einem `atomic`-Objekt in einer angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ab.  
  
```
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` enthalten ist.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Verwenden Sie nicht `memory_order_release` oder `memory_order_acq_rel`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der abgerufene Wert, der in `Atom`-gespeichert wird.  
  
##  <a name="atomic_signal_fence"></a> atomic_signal_fence  
 Fungiert als *Umgrenzung* (das ist eine Arbeitsspeicher-Synchronisierungsprimitive, mit der die Reihenfolge zwischen Lade- bzw. Speichervorgängen erzwungen wird) zwischen anderen Umgrenzungen in einem aufrufenden Thread, die über im gleichen Thread ausgeführte Signalhandler verfügen.  
  
```
inline void atomic_signal_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Order`  
 Eine den Umgrenzungstyp bestimmende Speicheranordnungseinschränkung.  
  
### <a name="remarks"></a>Hinweise  
 Das `Order`-Argument bestimmt den Umgrenzungstyp.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Die Umgrenzung hat keine Auswirkung.|  
|`memory_order_consume`|Die Umgrenzung ist eine Abrufumgrenzung.|  
|`memory_order_acquire`|Die Umgrenzung ist eine Abrufumgrenzung.|  
|`memory_order_release`|Die Umgrenzung ist eine Releaseumgrenzung.|  
|`memory_order_acq_rel`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung.|  
|`memory_order_seq_cst`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung, und sie ist sequenziell konsistent.|  
  
##  <a name="atomic_store"></a> atomic_store  
 Speichert einen Wert atomisch in einem atomischen Objekt.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein atomisches Objekt, das einen Wert vom Typ `Ty` enthält.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="remarks"></a>Hinweise  
 `atomic_store` speichert `Value` in dem Objekt, auf das von `Atom` innerhalb der `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkung gezeigt wird.  
  
##  <a name="atomic_store_explicit"></a> atomic_store_explicit  
 Speichert einen Wert atomisch in einem atomischen Objekt.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom, 
    Ty Value, 
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom, 
    T Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Atom`  
 Ein Zeiger auf ein `atomic`-Objekt, in dem ein Wert des Typs `Ty` enthalten ist.  
  
 `Value`  
 Ein Wert vom Typ `Ty`.  
  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Verwenden Sie nicht `memory_order_consume`, `memory_order_acquire`, oder `memory_order_acq_rel`.  
  
### <a name="remarks"></a>Hinweise  
 `atomic_store` speichert `Value` in dem Objekt, auf das innerhalb der von `Atom` angegebenen `memory_order` von `Order` gezeigt wird.  
  
##  <a name="atomic_thread_fence"></a> atomic_thread_fence  
 Fungiert als *Umgrenzung*. Dabei handelt es sich um eine Arbeitsspeichersynchronisierungs-Primitive, mit der die Reihenfolge zwischen Lade- bzw. Speichervorgängen ohne einen zugeordneten atomischen Vorgang erzwungen wird.  
  
```
inline void atomic_thread_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Order`  
 Eine den Umgrenzungstyp bestimmende Speicheranordnungseinschränkung.  
  
### <a name="remarks"></a>Hinweise  
 Das `Order`-Argument bestimmt den Umgrenzungstyp.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Die Umgrenzung hat keine Auswirkung.|  
|`memory_order_consume`|Die Umgrenzung ist eine Abrufumgrenzung.|  
|`memory_order_acquire`|Die Umgrenzung ist eine Abrufumgrenzung.|  
|`memory_order_release`|Die Umgrenzung ist eine Releaseumgrenzung.|  
|`memory_order_acq_rel`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung.|  
|`memory_order_seq_cst`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung, und sie ist sequenziell konsistent.|  
  
##  <a name="kill_dependency"></a> kill_dependency  
 Entfernt eine Abhängigkeit.  
  
```
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Arg`  
 Ein Wert vom Typ `Ty`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist `Arg`. Die Auswertung von `Arg` enthält keine Abhängigkeit vom Funktionsaufruf. Durch Unterbrechen einer möglichen Abhängigkeitskette könnte die Funktion zulassen, dass der Compiler effizienteren Code generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [\<atomic>](../standard-library/atomic.md)




