---
title: lock_guard-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs: C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c337d4188ccbc26280db59feab30ab7c11133bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
## <a name="members"></a>Member  
  
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



