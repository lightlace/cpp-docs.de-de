---
title: Event-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f858bfad08ca8d62c42556c54b505908b7122569
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="event-class"></a>event-Klasse
Ein Ereignis für manuelles Zurücksetzen, das explizit die Concurrency Runtime beachtet.  
  
## <a name="syntax"></a>Syntax  
  
```
class event;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ Event-Destruktor](#dtor)|Zerstört ein Ereignis.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[reset](#reset)|Setzt das Ereignis auf einen nicht signalisierten Zustand zurück.|  
|[set](#set)|Signalisiert das Ereignis.|  
|[Warte](#wait)|Wartet, bis das Ereignis signalisiert wird.|  
|[wait_for_multiple](#wait_for_multiple)|Wartet, bis mehrere Ereignisse signalisiert werden.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Strukturen für Synchronisierungsdaten](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `event`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>Ereignis 

 Erstellt ein neues Ereignis.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dtor"></a>~ Ereignis 

 Zerstört ein Ereignis.  
  
```
~event();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird erwartet, dass keine Threads auf das Ereignis warten, wenn der Destruktor ausgeführt wird. Wenn das Ereignis zerstört wird, während Threads auf das Ereignis warten, kann dies zu einem nicht definiertem Verhalten führen.  
  
##  <a name="reset"></a>Zurücksetzen 

 Setzt das Ereignis auf einen nicht signalisierten Zustand zurück.  
  
```
void reset();
```  
  
##  <a name="set"></a>Festlegen 

 Signalisiert das Ereignis.  
  
```
void set();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Signalisieren des Ereignisses kann möglicherweise dazu führen, dass eine beliebige Anzahl von Kontexten, die auf das Ereignis warten, ausführbar werden.  
  
##  <a name="timeout_infinite"></a>timeout_infinite 

 Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a>Warte 

 Wartet, bis das Ereignis signalisiert wird.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `_Timeout`  
 Gibt die Wartezeit in Millisekunden bis zum Timeout an. Der Wert `COOPERATIVE_TIMEOUT_INFINITE` gibt an, dass kein Timeout besteht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Wartezustand erfüllt wurde, wird der Wert `0` zurückgegeben. Andernfalls gibt der Wert `COOPERATIVE_WAIT_TIMEOUT` an, dass der Wartezustand durch einen Timeout beendet wurde, ohne dass das Ereignis signalisiert wurde.  
  
> [!IMPORTANT]
>  Rufen Sie [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] in einer `wait`-App nicht auf dem ASTA-Thread auf, da dieser Aufruf den aktuellen Thread blockieren kann und die App dadurch möglicherweise nicht mehr reagiert.  
  
##  <a name="wait_for_multiple"></a>wait_for_multiple 

 Wartet, bis mehrere Ereignisse signalisiert werden.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `_PPEvents`  
 Ein Array von Ereignissen, auf die gewartet werden soll. Die Anzahl der Ereignisse im Array wird durch den `count`-Parameter angegeben.  
  
 `count`  
 Die Anzahl von Ereignissen innerhalb des im `_PPEvents`-Parameter angegebenen Arrays.  
  
 `_FWaitAll`  
 Wenn der Parameter auf den Wert `true` festgelegt wird, gibt dies an, dass innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde, alle Ereignisse ausgelöst werden müssen, um den Wartevorgang zu beenden. Eine Festlegung auf den Wert `false` gibt an, dass jedes ausgelöste Ereignis innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde, für den Wartevorgang ausreichend ist.  
  
 `_Timeout`  
 Gibt die Wartezeit in Millisekunden bis zum Timeout an. Der Wert `COOPERATIVE_TIMEOUT_INFINITE` gibt an, dass kein Timeout besteht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Anforderungen des Wartevorgangs erfüllt wurden, ist dies der Index innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde und die Wartebedingung erfüllt hat. Andernfalls gibt der Wert `COOPERATIVE_WAIT_TIMEOUT` an, dass das Timeout für den Wartevorgang abgelaufen ist, ohne dass die Bedingung erfüllt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Parameter `_FWaitAll` auf den Wert `true` festgelegt wurde, um anzugeben, dass alle Ereignisse signalisiert werden müssen, um den Wartevorgang zu beenden, hat der von der Funktion zurückgegebene Index keine andere besondere Bedeutung außer der Tatsache, dass er nicht den Wert `COOPERATIVE_WAIT_TIMEOUT` darstellt.  
  
> [!IMPORTANT]
>  Rufen Sie [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] in einer `wait_for_multiple`-App nicht auf dem ASTA-Thread auf, da dieser Aufruf den aktuellen Thread blockieren kann und die App dadurch möglicherweise nicht mehr reagiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

