---
title: lock_guard-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 047c7ab9db009bceafe47bb0ae53b876adad81b5
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="lockguard-class"></a>lock_guard-Klasse
Stellt eine Vorlage dar, die zum Erstellen eines Objekts instanziiert werden kann, dessen Destruktor ein `mutex`-Objekt entsperrt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Mutex>
class lock_guard;
```  
  
## <a name="remarks"></a>Hinweise  
 Das Vorlagenargument `Mutex` muss einem *Mutex-Typ* benennen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`lock_guard::mutex_type`|Synonym für das Vorlagenargument `Mutex`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[lock_guard](#lock_guard)|Erstellt ein `lock_guard`-Objekt.|  
|[lock_guard::~lock_guard Destruktor](#dtorlock_guard_destructor)|Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Mutex >  
  
 **Namespace:** std  
  
##  <a name="lock_guard"></a> lock_guard::lock_guard-Konstruktor  
 Erstellt ein `lock_guard`-Objekt.  
  
```cpp  
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```  
  
### <a name="parameters"></a>Parameter  
 `Mtx`  
 Ein *mutex type*-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein Objekt des Typs `lock_guard` und sperrt `Mtx`. Wenn `Mtx` keinem rekursiven Mutex entspricht, muss dieses entsperrt werden, wenn dieser Konstruktor aufgerufen wird.  
  
 Der zweite Konstruktor sperrt nicht `Mtx`. `Mtx` muss gesperrt werden, wenn dieser Konstruktor aufgerufen wird. Der Konstruktor löst keine Ausnahmen aus.  
  
##  <a name="dtorlock_guard_destructor"></a> lock_guard::~lock_guard-Destruktor  
 Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.  
  
```
~lock_guard() noexcept;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das `mutex`-Objekt nicht vorhanden ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




