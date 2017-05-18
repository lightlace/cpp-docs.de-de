---
title: timed_mutex-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
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
ms.openlocfilehash: 40622e83235c4df32ec9afd25905ffdde2b97be7
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="timedmutex-class"></a>timed_mutex-Klasse
Stellt einen *timed mutex type* dar. Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss durch zeitlich begrenzte Blockierung innerhalb eines Programms zu erzwingen.  
  
## <a name="syntax"></a>Syntax  
  
```
class timed_mutex;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[timed_mutex](#timed_mutex)|Erstellt ein `timed_mutex`-Objekt, das nicht gesperrt ist.|  
|[timed_mutex::~timed_mutex-Destruktor](#dtortimed_mutex_destructor)|Gibt alle Ressourcen frei, die vom `timed_mutex`-Objekt verwendet werden.|  
  
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
  
##  <a name="lock"></a>timed_mutex:: lock
 Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="timed_mutex"></a> timed_mutex::timed_mutex-Konstruktor  
 Erstellt ein `timed_mutex`-Objekt, das nicht gesperrt ist.  
  
```cpp  
timed_mutex();
```  
  
##  <a name="dtortimed_mutex_destructor"></a> timed_mutex::~timed_mutex-Destruktor  
 Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet werden.  
  
```cpp  
~timed_mutex();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.  
  
##  <a name="try_lock"></a>timed_mutex:: try_lock
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="try_lock_for"></a>timed_mutex:: try_lock_for
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parameter  
 `Rel_time`  
 Ein [chrono::duration](../standard-library/duration-class.md)-Objekt, das angibt, wie lange die Methode höchstens versucht, in den Besitz von `mutex` zu gelangen.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="try_lock_until"></a>timed_mutex:: try_lock_until
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
 `true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="unlock"></a>timed_mutex:: Unlock
 Gibt den Besitz von `mutex` frei.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




