---
title: promise-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::promise
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ad79ecc3497182a451ef85ea53c8ec5603fdca69
ms.lasthandoff: 02/24/2017

---
# <a name="promise-class"></a>promise-Klasse
Beschreibt einen *asynchronen Anbieter*.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
class promise;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[promise::promise-Konstruktor](#promise__promise_constructor)|Erstellt ein `promise`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[promise::get_future](#promise__get_future_method)|Gibt eine dieser Zusage zugeordnete [Zukunft](../standard-library/future-class.md) zurück.|  
|[promise::set_exception](#promise__set_exception_method)|Legt das Ergebnis dieser Zusage atomisch zum Angeben einer Ausnahme fest.|  
|[promise::set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)|Legt das Ergebnis dieser Zusage zum Angeben einer Ausnahme atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).|  
|[promise::set_value](#promise__set_value_method)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest.|  
|[promise::set_value_at_thread_exit](#promise__set_value_at_thread_exit_method)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).|  
|[promise::swap](#promise__swap_method)|Tauscht den *zugeordneten asynchronen Zustand* dieser Zusage mit dem eines angegebenen Zusageobjekts aus.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[promise::operator=](#promise__operator_eq)|Zuweisung des Freigabestatus dieses Zusageobjekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `promise`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
##  <a name="a-namepromisegetfuturemethoda--promisegetfuture"></a><a name="promise__get_future_method"></a> promise::get_future  
 Gibt ein [Zukunft](../standard-library/future-class.md)-Objekt zurück, das über den gleichen *zugeordneten asynchronen Zustand* wie die Zusage verfügt.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Zusageobjekt leer ist, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem [error_code](../standard-library/error-code-class.md) von `no_state` aus.  
  
 Wenn diese Methode bereits für ein Zusageobjekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode `future_error` mit `error_code` von `future_already_retrieved` aus.  
  
##  <a name="a-namepromiseoperatoreqa--promiseoperator"></a><a name="promise__operator_eq"></a> promise::operator=  
 Überträgt den *zugeordneten asynchronen Zustand* aus einem angegebenen `promise`-Objekt.  
  
```
promise& operator=(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Other`  
 Ein `promise`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `*this`  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator überträgt den zugeordneten asynchronen Zustand von `Other`. Nach der Übertragung ist `Other` *leer*.  
  
##  <a name="a-namepromisepromiseconstructora--promisepromise-constructor"></a><a name="promise__promise_constructor"></a> promise::promise-Konstruktor  
 Erstellt ein `promise`-Objekt.  
  
```
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Al`  
 Eine Speicherbelegung. Siehe [\<allocators>](../standard-library/allocators-header.md) für weitere Informationen.  
  
 `Other`  
 Ein `promise`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein *leeres*`promise`-Objekt.  
  
 Der zweite Konstruktor erstellt ein leeres `promise`-Objekt und verwendet `Al` für Arbeitsspeicherbelegung.  
  
 Der dritte Konstruktor erstellt ein `promise`-Objekt, und der zugeordnete asynchrone Zustand wird von `Other` übertragen und lässt `Other` leer.  
  
##  <a name="a-namepromisesetexceptionmethoda--promisesetexception"></a><a name="promise__set_exception_method"></a> promise::set_exception  
 Es wird atomisch eine Ausnahme als Ergebnis dieses `promise`-Objekts gespeichert, und der *entsprechende asynchrone Zustand* wird auf *fertig* festgelegt.  
  
```
void set_exception(exception_ptr Exc);
```  
  
### <a name="parameters"></a>Parameter  
 `Exc`  
 Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), der von dieser Methode als Ausnahmeergebnis gespeichert ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `promise`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn `set_exception`, [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method), [set_value](#promise__set_value_method) oder [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Aufgrund dieser Methode wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.  
  
##  <a name="a-namepromisesetexceptionatthreadexitmethoda--promisesetexceptionatthreadexit"></a><a name="promise__set_exception_at_thread_exit_method"></a> promise::set_exception_at_thread_exit  
 Legt das Ergebnis von `promise` zum Angeben einer Ausnahme atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).  
  
```
void set_exception_at_thread_exit(exception_ptr Exc);
```  
  
### <a name="parameters"></a>Parameter  
 `Exc`  
 Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), der von dieser Methode als Ausnahmeergebnis gespeichert ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Zusageobjekt über keinen *zugeordneten asynchronen Zustand* verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn [, ](#promise__set_exception_method)set_exception`set_exception_at_thread_exit`, [set_value](#promise__set_value_method) oder [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Im Gegensatz zu [set_exception](#promise__set_exception_method) wird der asynchrone zugeordnete Zustand von dieser Methode nicht auf „fertig“ festgelegt, bis alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.  
  
##  <a name="a-namepromisesetvaluemethoda--promisesetvalue"></a><a name="promise__set_value_method"></a> promise::set_value  
 Es wird atomisch ein Wert als Ergebnis dieses `promise`-Objekts gespeichert, und der *entsprechende asynchrone Zustand* wird auf *fertig* festgelegt.  
  
```
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```  
  
### <a name="parameters"></a>Parameter  
 `Val`  
 Der als Ergebnis zu speichernde Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `promise`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn [set_exception](#promise__set_exception_method), [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method), `set_value` oder [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Aufgrund dieser Methode wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.  
  
 Die erste Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn `Val` in den zugeordneten asynchronen Zustand kopiert wird. In dieser Situation wird der zugeordnete asynchrone Zustand nicht auf "vorbereitet" festgelegt.  
  
 Die zweite Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn `Val` in den zugeordneten asynchronen Zustand verschoben wird. In dieser Situation wird der zugeordnete asynchrone Zustand nicht auf "vorbereitet" festgelegt.  
  
 Für die teilweise Spezialisierung `promise<Ty&>`, ist der gespeicherte Wert tatsächlich ein Verweis auf `Val`.  
  
 Für die Spezialisierung `promise<void>` ist kein gespeicherter Wert vorhanden.  
  
##  <a name="a-namepromisesetvalueatthreadexitmethoda--promisesetvalueatthreadexit"></a><a name="promise__set_value_at_thread_exit_method"></a> promise::set_value_at_thread_exit  
 Speichert einen Wert atomisch als Ergebnis dieses `promise`-Objekts.  
  
```
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```  
  
### <a name="parameters"></a>Parameter  
 `Val`  
 Der als Ergebnis zu speichernde Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Zusageobjekt über keinen *zugeordneten asynchronen Zustand* verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.  
  
 Wenn [set_exception](#promise__set_exception_method), [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method), [set_value](#promise__set_value_method) oder `set_value_at_thread_exit` bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.  
  
 Im Gegensatz zu `set_value`, wird der zugeordnete asynchrone Zustand erst auf "vorbereitet" festgelegt, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.  
  
 Die erste Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn `Val` in den zugeordneten asynchronen Zustand kopiert wird.  
  
 Die zweite Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn `Val` in den zugeordneten asynchronen Zustand verschoben wird.  
  
 Für die teilweise Spezialisierung `promise<Ty&>`, ist der gespeicherte Wert tatsächlich ein Verweis auf `Val`.  
  
 Für die Spezialisierung `promise<void>` ist kein gespeicherter Wert vorhanden.  
  
##  <a name="a-namepromiseswapmethoda--promiseswap"></a><a name="promise__swap_method"></a> promise::swap  
 Tauscht den *zugeordneten asynchronen Zustand* dieses Zusageobjekts mit dem eines angegebenen Objekts aus.  
  
```
void swap(promise& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Other`  
 Ein `promise`-Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)




 


