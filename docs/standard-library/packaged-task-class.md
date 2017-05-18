---
title: packaged_task-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3ca8c4c008daa02af2bba0df8468bea3c063c28a
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="packagedtask-class"></a>packaged_task-Klasse
Beschreibt einen *asynchronen Anbieter*, der ein Aufrufwrapper und dessen Aufrufsignatur `Ty(ArgTypes...)` ist. Der *zugehörige asynchrone Zustand*  enthält zusätzlich zum potentiellen Ergebnis eine Kopie des aufrufbaren Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[packaged_task](#packaged_task)|Erstellt ein `packaged_task`-Objekt.|  
|[packaged_task::~packaged_task-Destruktor](#dtorpackaged_task_destructor)|Zerstört ein `packaged_task`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_future](#get_future)|Gibt ein [future](../standard-library/future-class.md)-Objekt zurück, das über den gleichen zugeordneten asynchronen Zustand verfügt.|  
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist und speichert automatisch den zurückgegebenen Wert.|  
|[reset](#reset)|Ersetzt den zugeordneten asynchronen Zustand.|  
|[swap](#swap)|Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.|  
|[gültige](#valid)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[packaged_task::operator=](#op_eq)|Überträgt einen zugeordneten asynchronen Zustand aus einem angegebenen Objekt.|  
|[packaged_task::operator()](#op_call)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist, speichert den zurückgegebenen Wert atomar und legt den Zustand auf *bereit* fest.|  
|[packaged_task::operator bool](#op_bool)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<zukünftige >  
  
 **Namespace:** std  
  
##  <a name="get_future"></a> packaged_task::get_future  
 Gibt ein `future<Ty>`-Objekt zurück, das über den gleichen *zugeordneten asynchronen Zustand* verfügt.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `future_already_retrieved` aus.  
  
##  <a name="make_ready_at_thread_exit"></a> packaged_task::make_ready_at_thread_exit  
 Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist und den Rückgabewert atomar speichert.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode oder [make_ready_at_thread_exit](#make_ready_at_thread_exit) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Jeder Rückgabewert wird atomar als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands gespeichert.  
  
 Im Gegensatz zu [packaged_task::operator()](#op_call), wird der zugeordnete asynchrone Zustand erst auf `ready` festgelegt, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.  
  
##  <a name="op_eq"></a> packaged_task::operator=  
 Überträgt den *zugeordneten asynchronen Zustand* aus einem angegebenen Objekt.  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `packaged_task`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `*this`  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Vorgang verfügt `Right` über keinen asynchron zugeordneten Zustand mehr.  
  
##  <a name="op_call"></a> packaged_task::operator()  
 Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist, den Rückgabewert atomar speichert und den Zustand auf *bereit* festlegt.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode oder [make_ready_at_thread_exit](#make_ready_at_thread_exit) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Alle Rückgabewerte werden als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands atomar gespeichert wird, und der Status wird auf bereit festgelegt. Deshalb wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.  
  
##  <a name="op_bool"></a> packaged_task::operator bool  
 Gibt an, ob das Objekt über `associated asynchronous state` verfügt.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
##  <a name="packaged_task"></a> packaged_task::packaged_task-Konstruktor  
 Erstellt ein `packaged_task`-Objekt.  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `packaged_task`-Objekt.  
  
 `alloc`  
 Eine Speicherbelegung. Siehe [\<allocators>](../standard-library/allocators-header.md) für weitere Informationen.  
  
 `fn`  
 Ein Funktionsobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein `packaged_task`-Objekt, das über keinen *zugeordneten asynchronen Zustand* verfügt.  
  
 Mit dem zweiten Konstruktor wird ein `packaged_task`-Objekt erstellt, und der zugeordnete asynchrone Zustand wird von `Right` übertragen. Nach dem Vorgang verfügt `Right` über keinen asynchron zugeordneten Zustand mehr.  
  
 Mit dem dritten Konstruktor wird ein `packaged_task`-Objekt erstellt, das über eine in dessen zugeordnetem asynchronen Zustand gespeicherten Kopie von `fn` verfügt.  
  
 Mit dem vierten Konstruktor wird ein `packaged_task`-Objekt erstellt, das über eine Kopie in dessen zugeordnetem asynchronen Zustand gespeicherten `fn` verfügt und `alloc` als Speicherbelegung verwendet.  
  
##  <a name="dtorpackaged_task_destructor"></a> packaged_task::~packaged_task-Destruktor  
 Zerstört ein `packaged_task`-Objekt.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der *zugeordnete asynchrone Zustand* nicht *bereit* ist, speichert der Destruktor eine [future_error](../standard-library/future-error-class.md)-Ausnahme, die über den Fehlercode `broken_promise` als Ergebnis im zugeordneten asynchronen Zustand verfügt, und alle Threads, die auf dem zugeordneten asynchronen Zustand blockiert sind, werden aufgehoben.  
  
##  <a name="reset"></a> packaged_task::reset  
 Verwendet einen neuen *zugeordneten asynchronen Zustand* zum Ersetzen des vorhandenen zugeordneten asynchronen Zustands.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt tatsächlich `*this = packaged_task(move(fn))` aus, wobei *fn* das Funktionsobjekt ist, das im zugeordneten asynchronen Zustand dieses Objekts gespeichert ist. Daher wird der Zustand des Objekts deaktiviert, und [get_future](#get_future), [operator()](#op_call) und [make_ready_at_thread_exit](#make_ready_at_thread_exit) können aufgerufen werden, als ob sie sich auf einem neu erstellten Objekt befinden würden.  
  
##  <a name="swap"></a> packaged_task::swap  
 Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `packaged_task`-Objekt.  
  
##  <a name="valid"></a> packaged_task::valid  
 Gibt an, ob das Objekt über `associated asynchronous state` verfügt.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




