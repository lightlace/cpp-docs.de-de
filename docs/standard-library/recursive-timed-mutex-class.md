---
title: recursive_timed_mutex-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
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
ms.openlocfilehash: 898661756cd21f362dc9d83dee6dab9b0c16fb8f
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex-Klasse
Stellt einen *timed_mutex-Typ* dar. Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss durch zeitlich begrenzte Blockierung innerhalb eines Programms zu erzwingen. Im Gegensatz zu Objekten des Typs [timed_mutex](../standard-library/timed-mutex-class.md), sind die Auswirkungen von aufrufenden Sperrmethoden für `recursive_timed_mutex`-Objekte klar definiert.  
  
## <a name="syntax"></a>Syntax  
  
```
class recursive_timed_mutex;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[recursive_timed_mutex](#recursive_timed_mutex)|Erstellt ein `recursive_timed_mutex`-Objekt, das nicht gesperrt ist.|  
|[recursive_timed_mutex-Destruktor](#dtorrecursive_timed_mutex_destructor)|Gibt alle Ressourcen frei, die vom `recursive_timed_mutex`-Objekt verwendet werden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[lock](#lock)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|  
|[try_lock](#try_lock)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|  
|[try_lock_for](#try_lock_for)|Versucht, den Besitz von `mutex` für ein angegebenes Zeitintervall zu erlangen.|  
|[try_lock_until](#try_lock_until)|Versucht, den Besitz von `mutex` bis zu einem angegebenen Zeitpunkt zu erlangen.|  
|[unlock](#unlock)|Gibt den Besitz von `mutex` frei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Mutex >  
  
 **Namespace:** std  
  
##  <a name="lock"></a> lock  
 Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, wird die Methode sofort zurückgegeben, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="recursive_timed_mutex"></a> recursive_timed_mutex-Konstruktor  
 Erstellt ein `recursive_timed_mutex`-Objekt, das nicht gesperrt ist.  
  
```cpp  
recursive_timed_mutex();
```  
  
##  <a name="dtorrecursive_timed_mutex_destructor"></a> ~recursive_timed_mutex-Destruktor  
 Gibt alle Ressourcen frei, die vom `recursive_timed_mutex`-Objekt verwendet werden.  
  
```cpp  
~recursive_timed_mutex();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.  
  
##  <a name="try_lock"></a> try_lock  
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode den Besitz von `mutex` erfolgreich erhalten hat oder wenn der aufrufende Thread bereits im Besitz der `mutex` ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, gibt die Funktion sofort `true` zurück, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="try_lock_for"></a> try_lock_for  
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parameter  
 `Rel_time`  
 Ein [chrono::duration](../standard-library/duration-class.md)-Objekt, das angibt, wie lange die Methode höchstens versucht, in den Besitz von `mutex` zu gelangen.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich Besitzrechte von `mutex` erhält, oder wenn der aufrufende Thread bereits im Besitz der `mutex` ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, gibt die Methode sofort `true` zurück, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="try_lock_until"></a> try_lock_until  
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Parameter  
 `Abs_time`  
 Ein Zeitpunkt, der den Schwellenwert angibt, nach dem die Methode nicht mehr versucht, in den Besitz von `mutex` zu gelangen.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich Besitzrechte von `mutex` erhält, oder wenn der aufrufende Thread bereits im Besitz der `mutex` ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, gibt die Methode sofort `true` zurück, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="unlock"></a> unlock  
 Gibt den Besitz von `mutex` frei.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt den Besitz der `mutex` erst frei, wenn sie so oft aufgerufen wurde, wie [lock](#lock), [try_lock](#try_lock) [try_lock_for](#try_lock_for), und [try_lock_until](#try_lock_until) erfolgreich im `recursive_timed_mutex`-Objekt aufgerufen wurden.  
  
 Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




