---
title: thread-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
dev_langs:
- C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: 16
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
ms.openlocfilehash: b1c5282d284a70917c6c14511bacda305180d778
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="thread-class"></a>thread-Klasse
Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class thread;
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können ein `thread`-Objekt zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung verwenden. Ein Threadobjekt, das mithilfe eines Standardkonstruktors erstellt wird, ist keinem Ausführungsthread zugeordnet. Mit einem Threadobjekt, das mithilfe eines aufrufbaren Objekts erstellt wird, wird ein neuer Ausführungsthread erstellt, und das aufrufbare Objekt in diesem Thread wird aufgerufen. Threadobjekte können verschoben aber nicht kopiert werden. Daher kann ein Ausführungsthread nur einem Threadobjekt zugeordnet werden.  
  
 Jeder Ausführungsthread besitzt einen eindeutigen Bezeichner des Typs `thread::id`. Die `this_thread::get_id`-Funktion gibt den Bezeichner des aufrufenden Threads zurück. Die `thread::get_id`-Memberfunktion gibt den Bezeichner des von einem Threadobjekt verwalteten Threads zurück. Ein nach Standard erstelltes Threadobjekt gibt die `thread::get_id`-Methode ein Objekt zurück, das über einen Wert verfügt, der für alle nach Standard erstellten Threadobjekte gleich ist und sich von dem von `this_thread::get_id` zurückgegebenen Wert für jeden Ausführungsthread, der zum Zeitpunkt des Aufrufs verknüpft werden kann, unterschiedet.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[thread::id-Klasse](#id_class)|Identifiziert den zugeordneten Thread eindeutig.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[thread](#thread)|Erstellt ein `thread`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Trennen](#detach)|Trennt den zugeordneten Thread vom `thread`-Objekt.|  
|[get_id](#get_id)|Gibt den eindeutigen Bezeichner des zugeordneten Threads zurück.|  
|[hardware_concurrency](#hardware_concurrency)|Statisch Gibt eine Schätzung der Anzahl von Hardwarethreadkontexten zurück.|  
|[join](#join)|Blockiert, bis der zugeordnete Thread abgeschlossen ist.|  
|[beigetreten](#joinable)|Gibt an, ob dem zugehörigen Thread beigetreten werden kann.|  
|[native_handle](#native_handle)|Gibt den implementierungsspezifischen Typ zurück, der das Threadhandle darstellt.|  
|[swap](#swap)|Tauscht den Objektzustand mit einem angegebenen `thread`-Objekt aus.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[thread::operator=](#op_eq)|Weist einem Thread das aktuelle `thread`-Objekt zu.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Thread >  
  
 **Namespace:** std  
  
##  <a name="detach"></a>Thread:: Detach
 Trennt den zugeordneten Thread. Das Betriebssystem wird zum Freigeben von Threadressourcen zuständig.  
  
```
void detach();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von `detach` geben nachfolgende Aufrufe von [Get_id](#get_id) [id](#id_class) zurück.  
  
 Wenn der Thread, der dem aufrufenden Objekt zugeordnet ist, nicht beitreten kann, löst die Funktion einen [system_error](../standard-library/system-error-class.md)-Fehler mit Fehlercode `invalid_argument` aus.  
  
 Wenn der Thread, der dem aufrufenden Objekt zugeordnet ist, ungültig ist, löst die Funktion einen `system_error` mit Fehlercode `no_such_process` aus.  
  
##  <a name="get_id"></a>Thread:: get_id
 Gibt den eindeutigen Bezeichner für den zugeordneten Threads zurück.  
  
```
id get_id() const noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [thread::id](#id_class)-Objekt, das den zugeordneten Thread eindeutig ausweist, oder `thread::id()`, wenn kein Thread dem Objekt zugeordnet ist.  
  
##  <a name="hardware_concurrency"></a>Thread:: hardware_concurrency
 Statische Methode, diet eine Schätzung der Anzahl von Hardwarethreadkontexten zurückgibt.  
  
```
static unsigned int hardware_concurrency() noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schätzung der Anzahl von Hardwarethreadkontexten. Wenn der Wert nicht berechnet werden kann oder nicht klar definiert ist, gibt diese Methode 0 zurück.  
  
##  <a name="id_class"></a> thread::id-Klasse  
 Stellt einen eindeutigen Bezeichner für jeden Thread der Ausführung im Prozess bereit.  
  
```
class thread::id {
    id() noexcept;
};
```  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor erstellt ein Objekt, das nicht gleich dem `thread::id`-Objekt für die vorhandenen Threads ist.  
  
 Alle mit dem Standwert konstruierten `thread::id`-Objekte gelten als gleich.  
  
##  <a name="join"></a>Thread:: Join
 Blockiert, bis der Thread der Ausführung, der das aufrufende Objekt zugeordnet wurde, abgeschlossen ist.  
  
```
void join();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Aufruf erfolgreich ist, geben nachfolgende Aufrufe von [get_id](#get_id) für das aufrufende Objekt eine Standard-[Thread:: ID](#id_class) zurück, die nicht gleich `thread::id` eines beliebigen vorhandenen Threads ist. Wenn der Aufruf nicht erfolgreich ist, ist der Wert, der von `get_id` zurückgegeben wird, unverändert.  
  
##  <a name="joinable"></a>Thread:: joinable
 Gibt an, ob dem zugeordneten Thread *beigetreten* werden kann.  
  
```
bool joinable() const noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn dem zugeordneten Thread *beigetreten* werden kann; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Einem Thread-Objekt kann *beigetreten* werden, wenn `get_id() != id()`.  
  
##  <a name="native_handle"></a>Thread:: native_handle
 Gibt den implementierungsspezifischen Typ zurück, der das Threadhandle darstellt. Das Threadhandle kann je nach Implementierung auf die jeweils entsprechende Weise verwendet werden.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `native_handle_type` ist als Win32-`HANDLE` definiert, das als `void *` umgewandelt wird.  
  
##  <a name="op_eq"></a> thread::operator=  
 Ordnet den Thread für das angegebene Objekt dem aktuellen Objekt zu.  
  
```
thread& operator=(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Other`  
 Ein `thread`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `*this`  
  
### <a name="remarks"></a>Hinweise  
 Die Methodenaufrufe trennen, wenn dem aufrufenden Objekt beigetreten werden kann.  
  
 Nach dem Erstellen die Zuordnung wird `Other` auf einen standardmäßig konstruierten Zustand festgelegt.  
  
##  <a name="swap"></a>Thread:: Swap
 Tauscht den Objektzustand mit dem eines angegebenen `thread`-Objekts aus.  
  
```
void swap(thread& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Other`  
 Ein `thread`-Objekt.  
  
##  <a name="thread"></a> thread::thread-Konstruktor  
 Erstellt ein `thread`-Objekt.  
  
```
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `F`  
 Eine anwendungsdefinierte Funktion, die vom Thread ausgeführt werden soll.  
  
 `A`  
 Eine Liste von Argumenten, die an `F` übergeben werden sollen.  
  
 `Other`  
 Ein vorhandenes `thread`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein Objekt, das nicht einem Thread der Ausführung zugeordnet ist. Der Wert, der durch einen Aufruf von `get_id` für das erstellte Objekt zurückgegeben wird, ist `thread::id()`.  
  
 Der zweite Konstruktor erstellt ein Objekt, das einem neuen Thread der Ausführung zugeordnet ist und die Pseudofunktion `INVOKE` ausführt, die in [\<functional>](../standard-library/functional.md) definiert ist. Wenn nicht genügend Ressourcen zum Starten eines neuen Threads verfügbar sind, löst die Funktion ein [system_error](../standard-library/system-error-class.md)-Objekt mit dem Fehlercode `resource_unavailable_try_again` aus. Wenn der Aufruf von `F` mit einer nicht abgefangenen Ausnahme beendet wird, wird [terminate](../standard-library/exception-functions.md#terminate) aufgerufen.  
  
 Der dritte Konstruktor erstellt ein Objekt, das mit dem Thread verknüpft ist, der `Other` zugeordnet ist. `Other` wird dann auf einen standardmäßig konstruierten Zustand festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)




