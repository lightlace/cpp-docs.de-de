---
title: mutex-Klasse (C++-Standardbibliothek)| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ff3e7e71c678ffc9bdead79ec56ad94f8e297a16
ms.lasthandoff: 02/24/2017

---
# <a name="mutex-class-c-standard-library"></a>mutex-Klasse (C++-Standardbibliothek)
Stellt einen *mutex-Typ* dar. Objekte dieses Typs können dazu verwendet werden, den gegenseitigen Ausschluss innerhalb eines Programms zu erzwingen.  
  
## <a name="syntax"></a>Syntax  
  
```
class mutex;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[mutex::mutex Constructor (mutex::mutex-Konstruktor)](#mutex__mutex_constructor)|Erstellt ein `mutex`-Objekt.|  
|[mutex::~mutex Destructor (mutex::~mutex-Destruktor)](#mutex___dtormutex_destructor)|Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet wurden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[mutex::lock Method (mutex::lock-Methode)](#mutex__lock_method)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|  
|[mutex::native_handle-Methode](#mutex__native_handle_method)|Gibt den implementierungsspezifischen Typ zurück, der das Mutexhandle darstellt.|  
|[mutex::try_lock-Methode](#mutex__try_lock_method)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|  
|[mutex::unlock-Methode](#mutex__unlock_method)|Gibt den Besitz von `mutex` frei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
##  <a name="a-namemutexlockmethoda--mutexlock-method"></a><a name="mutex__lock_method"></a>mutex::lock-Methode  
 Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="a-namemutexmutexconstructora--mutexmutex-constructor"></a><a name="mutex__mutex_constructor"></a>mutex::mutex-Konstruktor  
 Erstellt ein `mutex`-Objekt, das nicht gesperrt ist.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="a-namemutexdtormutexdestructora--mutexmutex-destructor"></a><a name="mutex___dtormutex_destructor"></a>mutex::~mutex-Destruktor  
 Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet werden.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.  
  
##  <a name="a-namemutexnativehandlemethoda--mutexnativehandle-method"></a><a name="mutex__native_handle_method"></a>mutex::native_handle-Methode  
 Gibt den implementierungsspezifischen Typ zurück, der das Mutexhandle darstellt. Das Mutexhandle kann je nach Implementierung auf die jeweils entsprechende Weise verwendet werden.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `native_handle_type` ist als `Concurrency::critical_section *` definiert, das als `void *` umgewandelt wird.  
  
##  <a name="a-namemutextrylockmethoda--mutextrylock-method"></a><a name="mutex__try_lock_method"></a> mutex::try_lock Method (mutex::try_lock-Methode  
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
##  <a name="a-namemutexunlockmethoda--mutexunlock-method"></a><a name="mutex__unlock_method"></a> mutex::unlock-Methode  
 Gibt den Besitz von `mutex` frei.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




