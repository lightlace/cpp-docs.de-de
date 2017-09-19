---
title: '&lt;shared_mutex&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <shared_mutex>
- shared_mutex/std::swap
- shared_mutex/std::shared_lock
- shared_mutex/std::shared_lock::shared_lock
- shared_mutex/std::shared_lock::operator=
- shared_mutex/std::shared_lock::operator =
- shared_mutex/std::shared_lock::lock
- shared_mutex/std::shared_lock::try_lock
- shared_mutex/std::shared_lock::try_lock_for
- shared_mutex/std::shared_lock::try_lock_until
- shared_mutex/std::shared_lock::unlock
- shared_mutex/std::shared_lock::swap
- shared_mutex/std::shared_lock::release
- shared_mutex/std::shared_lock::owns_lock
- shared_mutex/std::shared_lock::operator bool
- shared_mutex/std::shared_lock::mutex
- shared_mutex/std::shared_mutex
- shared_mutex/std::shared_mutex::native_handle_type
- shared_mutex/std::shared_mutex::shared_mutex
- shared_mutex/std::shared_mutex::operator=
- shared_mutex/std::shared_mutex::operator =
- shared_mutex/std::shared_mutex::lock
- shared_mutex/std::shared_mutex::try_lock
- shared_mutex/std::shared_mutex::unlock
- shared_mutex/std::shared_mutex::lock_shared
- shared_mutex/std::shared_mutex::try_lock_shared
- shared_mutex/std::shared_mutex::unlock_shared
- shared_mutex/std::shared_mutex::native_handle
- shared_mutex/std::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::operator=
- shared_mutex/std::shared_timed_mutex::operator =
- shared_mutex/std::shared_timed_mutex::lock
- shared_mutex/std::shared_timed_mutex::try_lock
- shared_mutex/std::shared_timed_mutex::try_lock_for
- shared_mutex/std::shared_timed_mutex::try_lock_until
- shared_mutex/std::shared_timed_mutex::unlock
- shared_mutex/std::shared_timed_mutex::lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared_for
- shared_mutex/std::shared_timed_mutex::try_lock_shared_until
- shared_mutex/std::shared_timed_mutex::unlock_shared
dev_langs:
- C++
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: e864aca13c5ae83b3806a95026a05f8f408e9071
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="ltsharedmutexgt"></a>&lt;shared_mutex&gt;
Der <shared_mutex>-Header bietet Synchronisierungsprimitive für den Schutz von freigegebenen Daten an, auf die mehrere Threads zugreifen können. Zusätzlich zu der exklusiven Zugriffssteuerung, die von Mutex-Klassen bereitgestellt wird, ermöglichen die gemeinsamen Mutex-Klassen auch den gemeinsamen Besitz durch mehrere Threads für den nicht exklusiven Zugriff. Gemeinsame Mutexe können verwendet werden, um Ressourcen zu steuern, die von mehreren Threads gelesen werden können, ohne dass eine Racebedingung verursacht wird, aber ausschließlich von einem einzelnen Thread geschrieben werden müssen.  
  
 Der Header <shared_mutex> definiert die Klassen `shared_mutex` und `shared_timed_mutex`, die Vorlagenklasse `shared_lock` und die Vorlagenfunktion `swap` für die gemeinsame Mutex-Unterstützung.  
  
|Klassen|Beschreibung|  
|-------------|-----------------|  
|[shared_mutex-Klasse](../standard-library/shared-mutex.md#class_shared_mutex)|Einen gemeinsamer Mutex-Typ, der von einem Agent exklusiv gesperrt oder nicht exklusiv von mehreren Agents gemeinsam verwendet werden kann.|  
|[shared_timed_mutex-Klasse](../standard-library/shared-mutex.md#class_shared_timed_mutex)|Einen gemeinsamer zeitgesteuerter Mutex-Typ, der von einem Agent exklusiv gesperrt oder nicht exklusiv von mehreren Agents gemeinsam verwendet werden kann.|  
|[shared_lock-Klasse](../standard-library/shared-mutex.md#class_shared_lock)|Eine Vorlagenklasse, die einen gemeinsamen Mutex zur Unterstützung von zeitgesteuerten Lock-Vorgängen und die nicht exklusive gemeinsame Verwendung von mehreren Agents umschließt.|  
  
|Funktionen|Beschreibung|  
|---------------|-----------------|  
|[swap](../standard-library/shared-mutex.md#function_swap)|Vertauscht den Inhalt von gemeinsamen Mutex-Objekten, auf die die Funktionsparameter verweisen.|  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
namespace std {
    class shared_mutex;
    class shared_timed_mutex;
    template <class Mutex>  
class shared_lock;
    template <class Mutex>  
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
}
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von Klasse `shared_mutex` ist ein *gemeinsamer Mutex-Typ*, ein Typ, der den gemeinsamen Besitz eines Mutex innerhalb eines Bereichs steuert. Ein gemeinsamer Mutex-Typ erfüllt alle Anforderungen eines Mutex-Typs sowie Member zur Unterstützung des gemeinsamem nicht exklusiven Besitzes.  
  
 Ein gemeinsamer Mutex unterstützt die zusätzlichen Methoden `lock_shared`, `unlock_shared` und `try_lock_shared`:  
  
-   Die `lock_shared`-Methode blockiert den aufrufenden Thread, bis der Thread den gemeinsamen Besitz des Mutex erlangt.  
  
-   Die `unlock_shared`-Methode gibt den Besitz des Mutex frei, in dem der aufrufende Thread steht.  
  
-   Die `try_lock_shared`-Methode versucht, ohne Blockierung in den Besitz des Mutex zu gelangen. Der Rückgabetyp ist in `bool` konvertierbar und weist den Wert `true` auf, wenn die Methode den Besitz erlangt, andernfalls `false`.  
  
 Die Klasse `shared_timed_mutex` ist ein *gemeinsamer zeitgesteuerter Mutex-Typ*, ein Typ, der die Anforderungen eines gemeinsamen Mutex-Typs und eines zeitgesteuerten Mutex-Typs erfüllt.  
  
 Ein gemeinsamer zeitgesteuerter Mutex-Typ unterstützt die zusätzlichen Methoden `try_lock_shared_for` und `try_lock_shared_until`:  
  
-   Die `try_lock_shared_for`-Methode versucht, den gemeinsamen Besitz des Mutex abzurufen, bis die vom Parameter angegebene Dauer verstrichen ist. Wenn die Dauer nicht positiv ist, entspricht die Methode `try_lock_shared`. Die Methode gibt nicht innerhalb der angegebenen Dauer zurück, sofern der gemeinsame Besitz nicht abgerufen wird. Der Rückgabewert ist `true`, wenn die Methode den gemeinsamen Besitz abruft, andernfalls ist er `false`.  
  
-   Die `try_lock_shared_until` Methode versucht, den gemeinsamen Besitz des Mutex abrufen, bis die angegebene absolute Zeit abgelaufen ist. Wenn die angegebene Zeit bereits verstrichen ist, entspricht die Methode `try_lock_shared`. Die Methode gibt nicht vor der angegebenen Zeit zurück, wenn der gemeinsame Besitz nicht abgerufen wird. Der Rückgabewert ist `true`, wenn die Methode den gemeinsamen Besitz abruft, andernfalls ist er `false`.  
  
 Die `shared_lock`-Vorlagenklasse erweitert die Unterstützung für das zeitgesteuerte Sperren und Übertragen des Besitzes an einen gemeinsamen Mutex. Der Besitz des Mutex kann bei oder nach der Erstellung abgerufen und an ein anderes `shared_lock`-Objekt übertragen werden. Objekte vom Typ `shared_lock` können verschoben, aber nicht kopiert werden.  
  
> [!WARNING]
>  Ab Visual Studio 2015, die C++-Standardbibliothek Synchronisierungstypen basieren auf Windows-Synchronisierungsprimitiven und verwenden ConcRT nicht mehr (außer wenn die Zielplattform Windows XP ist). Die in <mutex> definierten Typen dürfen nicht mit ConcRT-Typen oder -Funktionen verwendet werden.  
  
## <a name="classes"></a>Klassen  
  
###  <a name="class_shared_mutex"></a> shared_mutex-Klasse  
 Klasse `shared_mutex` implementiert einen nicht rekursiven Mutex mit gemeinsamer Besitzsemantik.  
  
```cpp  
class shared_mutex {
   public:
   shared_mutex();
   ~shared_mutex();
   shared_mutex(const shared_mutex&) = delete;
   shared_mutex& operator=(const shared_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   void unlock_shared();
   // Getters
   typedef void** native_handle_type; // implementation defined
   native_handle_type native_handle();
   };  
```

###  <a name="class_shared_timed_mutex"></a> shared_timed_mutex-Klasse  
 Klasse `shared_timed_mutex` implementiert einen nicht rekursiven Mutex mit gemeinsamer Besitz-Semantik, die den Anforderungen eines zeitgesteuerten Mutex-Typs entspricht.  
  
```cpp  
class shared_timed_mutex {
   public:
   shared_timed_mutex();
   ~shared_timed_mutex();
   shared_timed_mutex(const shared_timed_mutex&) = delete;
   shared_timed_mutex& operator=(const shared_timed_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   template \<class Rep, class Period>  
   bool try_lock_for(const chrono::duration\<Rep, Period>& rel_time);
   template \<class Clock, class Duration>  
   bool try_lock_until(const chrono::time_point\<Clock, Duration>& abs_time);
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   template \<class Rep, class Period>  
   bool try_lock_shared_for(const chrono::duration\<Rep, Period>& rel_time);
   template \<class Clock, class Duration>  
   bool try_lock_shared_until(const chrono::time_point\<Clock, Duration>& abs_time);
   void unlock_shared();
   };  
```

###  <a name="class_shared_lock"></a> shared_lock-Klasse  
 Vorlagenklasse `shared_lock` steuert den gemeinsamen Besitz eines gemeinsamen Mutex-Objekts innerhalb eines Bereichs. Bei dem Vorlagenparameter muss es sich um einen gemeinsamen Mutex-Typ handeln.  

```cpp  
class shared_lock {
   public:
   typedef Mutex mutex_type;
   shared_lock() noexcept;
   explicit shared_lock(mutex_type& m);
   // blocking
   shared_lock(mutex_type& m, defer_lock_t) noexcept;
   shared_lock(mutex_type& m, try_to_lock_t);
   shared_lock(mutex_type& m, adopt_lock_t);
   template \<class Clock, class Duration>  
   shared_lock(mutex_type& m,
   const chrono::time_point\<Clock, Duration>& abs_time);
   template \<class Rep, class Period>  
   shared_lock(mutex_type& m,
   const chrono::duration\<Rep, Period>& rel_time);
   ~shared_lock();
   shared_lock(shared_lock const&) = delete;
   shared_lock& operator=(shared_lock const&) = delete;
   shared_lock(shared_lock&& u) noexcept;
   shared_lock& operator=(shared_lock&& u) noexcept;
   void lock();
   // blocking
   bool try_lock();
   template \<class Rep, class Period>  
   bool try_lock_for(const chrono::duration\<Rep, Period>& rel_time);
   template \<class Clock, class Duration>  
   bool try_lock_until(const chrono::time_point\<Clock, Duration>& abs_time);
   void unlock();
   // Setters
   void swap(shared_lock& u) noexcept;
   mutex_type* release() noexcept;
   // Getters
   bool owns_lock() const noexcept;
   explicit operator bool () const noexcept;
   mutex_type* mutex() const noexcept;
   private:
   mutex_type* pm; // exposition only
   bool owns; // exposition only
   };  
```

## <a name="functions"></a>Funktionen  
  
###  <a name="function_swap"></a>Swap
 Tauscht die `shared_lock`-Objekte.  
  
```cpp  
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```  
  
 Tauscht den Inhalt von zwei `shared_lock`-Objekten aus. Identisch mit `x``.swap(``y``)`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<shared_mutex>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




