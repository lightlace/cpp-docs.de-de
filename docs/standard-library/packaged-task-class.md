---
title: packaged_task-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
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
translationtype: Machine Translation
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: a54b1c9788ef60f63aafafc9125b09c449fde1b0
ms.lasthandoff: 02/24/2017

---
# <a name="packagedtask-class"></a>packaged_task-Klasse
Beschreibt einen *asynchronen Anbieter*, der ein Aufrufwrapper und dessen Aufrufsignatur `Ty(ArgTypes...)` ist. Der *zugehörige asynchrone Zustand * enthält zusätzlich zum potentiellen Ergebnis eine Kopie des aufrufbaren Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[packaged_task::packaged_task-Konstruktor](#packaged_task__packaged_task_constructor)|Erstellt ein `packaged_task`-Objekt.|  
|[packaged_task::~packaged_task-Destruktor](#packaged_task___dtorpackaged_task_destructor)|Zerstört ein `packaged_task`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[packaged_task::get_future](#packaged_task__get_future_method)|Gibt ein [future](../standard-library/future-class.md)-Objekt zurück, das über den gleichen zugeordneten asynchronen Zustand verfügt.|  
|[packaged_task::make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist und speichert automatisch den zurückgegebenen Wert.|  
|[packaged_task::reset](#packaged_task__reset_method)|Ersetzt den zugeordneten asynchronen Zustand.|  
|[packaged_task::swap](#packaged_task__swap_method)|Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.|  
|[packaged_task::valid](#packaged_task__valid_method)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[packaged_task::operator=](#packaged_task__operator_eq)|Überträgt einen zugeordneten asynchronen Zustand aus einem angegebenen Objekt.|  
|[packaged_task::operator()](#packaged_task__operator__)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist, speichert den zurückgegebenen Wert atomar und legt den Zustand auf *bereit* fest.|  
|[packaged_task::operator bool](#packaged_task__operator_bool)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
##  <a name="a-namepackagedtaskgetfuturemethoda--packagedtaskgetfuture"></a><a name="packaged_task__get_future_method"></a> packaged_task::get_future  
 Gibt ein `future<Ty>`-Objekt zurück, das über den gleichen *zugeordneten asynchronen Zustand* verfügt.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `future_already_retrieved` aus.  
  
##  <a name="a-namepackagedtaskmakereadyatthreadexitmethoda--packagedtaskmakereadyatthreadexit"></a><a name="packaged_task__make_ready_at_thread_exit_method"></a> packaged_task::make_ready_at_thread_exit  
 Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist und den Rückgabewert atomar speichert.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode oder [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Jeder Rückgabewert wird atomar als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands gespeichert.  
  
 Im Gegensatz zu [packaged_task::operator()](#packaged_task__operator__), wird der zugeordnete asynchrone Zustand erst auf `ready` festgelegt, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.  
  
##  <a name="a-namepackagedtaskoperatoreqa--packagedtaskoperator"></a><a name="packaged_task__operator_eq"></a> packaged_task::operator=  
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
  
##  <a name="a-namepackagedtaskoperatora--packagedtaskoperator"></a><a name="packaged_task__operator__"></a> packaged_task::operator()  
 Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist, den Rückgabewert atomar speichert und den Zustand auf *bereit* festlegt.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn diese Methode oder [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Alle Rückgabewerte werden als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands atomar gespeichert wird, und der Status wird auf bereit festgelegt. Deshalb wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.  
  
##  <a name="a-namepackagedtaskoperatorboola--packagedtaskoperator-bool"></a><a name="packaged_task__operator_bool"></a> packaged_task::operator bool  
 Gibt an, ob das Objekt über `associated asynchronous state` verfügt.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
##  <a name="a-namepackagedtaskpackagedtaskconstructora--packagedtaskpackagedtask-constructor"></a><a name="packaged_task__packaged_task_constructor"></a> packaged_task::packaged_task-Konstruktor  
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
  
##  <a name="a-namepackagedtaskdtorpackagedtaskdestructora--packagedtaskpackagedtask-destructor"></a><a name="packaged_task___dtorpackaged_task_destructor"></a> packaged_task::~packaged_task-Destruktor  
 Zerstört ein `packaged_task`-Objekt.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der *zugeordnete asynchrone Zustand* nicht *bereit* ist, speichert der Destruktor eine [future_error](../standard-library/future-error-class.md)-Ausnahme, die über den Fehlercode `broken_promise` als Ergebnis im zugeordneten asynchronen Zustand verfügt, und alle Threads, die auf dem zugeordneten asynchronen Zustand blockiert sind, werden aufgehoben.  
  
##  <a name="a-namepackagedtaskresetmethoda--packagedtaskreset"></a><a name="packaged_task__reset_method"></a> packaged_task::reset  
 Verwendet einen neuen *zugeordneten asynchronen Zustand* zum Ersetzen des vorhandenen zugeordneten asynchronen Zustands.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt tatsächlich `*this = packaged_task(move(fn))` aus, wobei *fn* das Funktionsobjekt ist, das im zugeordneten asynchronen Zustand dieses Objekts gespeichert ist. Daher wird der Zustand des Objekts deaktiviert, und [get_future](#packaged_task__get_future_method), [operator()](#packaged_task__operator__) und [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) können aufgerufen werden, als ob sie sich auf einem neu erstellten Objekt befinden würden.  
  
##  <a name="a-namepackagedtaskswapmethoda--packagedtaskswap"></a><a name="packaged_task__swap_method"></a> packaged_task::swap  
 Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `packaged_task`-Objekt.  
  
##  <a name="a-namepackagedtaskvalidmethoda--packagedtaskvalid"></a><a name="packaged_task__valid_method"></a> packaged_task::valid  
 Gibt an, ob das Objekt über `associated asynchronous state` verfügt.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




