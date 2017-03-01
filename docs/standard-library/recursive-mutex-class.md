---
title: recursive_mutex-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: c82c8302be5d3e01de90adda2049a022100b8443
ms.lasthandoff: 02/24/2017

---
# <a name="recursivemutex-class"></a>recursive_mutex-Klasse
Stellt einen *mutex-Typ* dar. Das Verhalten von aufrufenden Sperrmethoden für Objekte, die bereits gesperrt sind, ist im Gegensatz zu [mutex](../standard-library/mutex-class-stl.md) klar definiert.  
  
## <a name="syntax"></a>Syntax  
  
```
class recursive_mutex;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[recursive_mutex-Konstruktor](#recursive_mutex__recursive_mutex_constructor)|Erstellt ein `recursive_mutex`-Objekt.|  
|[~recursive_mutex-Destruktor](#recursive_mutex___dtorrecursive_mutex_destructor)|Gibt alle Ressourcen frei, die vom `recursive_mutex`-Objekt verwendet werden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[lock](#recursive_mutex__lock_method)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von mutex gelangt.|  
|[try_lock](#recursive_mutex__try_lock_method)|Versucht, ohne Blockierung in den Besitz von mutex zu gelangen.|  
|[unlock](#recursive_mutex__unlock_method)|Gibt den Besitz von mutex frei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
##  <a name="a-namerecursivemutexlockmethoda--lock"></a><a name="recursive_mutex__lock_method"></a> lock  
 Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, wird die Methode sofort zurückgegeben, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="a-namerecursivemutexrecursivemutexconstructora--recursivemutex"></a><a name="recursive_mutex__recursive_mutex_constructor"></a> recursive_mutex  
 Erstellt ein `recursive_mutex`-Objekt, das nicht gesperrt ist.  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="a-namerecursivemutexdtorrecursivemutexdestructora--recursivemutex"></a><a name="recursive_mutex___dtorrecursive_mutex_destructor"></a> ~recursive_mutex  
 Gibt alle Ressourcen frei, die vom Objekt verwendet werden.  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.  
  
##  <a name="a-namerecursivemutextrylockmethoda--trylock"></a><a name="recursive_mutex__try_lock_method"></a> try_lock  
 Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Methode erfolgreich Besitzrechte von `mutex` erhält, oder wenn der aufrufende Thread bereits im Besitz der `mutex` ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, gibt die Funktion sofort `true` zurück, und die vorherige Sperre bleibt in Kraft.  
  
##  <a name="a-namerecursivemutexunlockmethoda--unlock"></a><a name="recursive_mutex__unlock_method"></a> unlock  
 Gibt den Besitz von mutex frei.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt den Besitz der `mutex` erst zurück, wenn sie so oft aufgerufen wurde, wie [lock](#recursive_mutex__lock_method) und [try_lock](#recursive_mutex__try_lock_method) erfolgreich im `recursive_mutex`-Objekt aufgerufen wurden.  
  
 Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




