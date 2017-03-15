---
title: '&lt;future&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: de302b9a2d971b2a39d4ce775799f27dd7244a5c
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt;-Funktionen
||||  
|-|-|-|  
|[get_id](#get_id_function)|[sleep_for](#sleep_for_function)|[sleep_until](#sleep_until_function)|  
|[swap](#swap_function)|[yield](#yield_function)|  
  
##  <a name="a-namegetidfunctiona--getid"></a><a name="get_id_function"></a> get_id  
 Weist den aktuellen Ausführungsthread eindeutig aus.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt vom Typ [Thread:: ID](../standard-library/thread-class.md), das den aktuellen Ausführungsthread eindeutig ausweist.  
  
##  <a name="a-namesleepforfunctiona--sleepfor"></a><a name="sleep_for_function"></a> sleep_for  
 Blockiert den aufrufenden Thread.  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parameter  
 `Rel_time`  
 Ein [Dauer](../standard-library/duration-class.md)-Objekt, das ein Zeitintervall angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion sperrt den aufrufenden Thread für mindestens die Zeit, die durch `Rel_time` angegeben wird. Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-namesleepuntilfunctiona--sleepuntil"></a><a name="sleep_until_function"></a> sleep_until  
 Blockiert den aufrufenden Thread mindestens bis zum angegebenen Zeitpunkt.  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>Parameter  
 `Abs_time`  
 Stellt einen Zeitpunkt dar.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löst keine Ausnahmen aus.  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a> swap  
 Vertauscht die Zustände von zwei `thread`-Objekten.  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `thread`-Objekt.  
  
 `Right`  
 Das rechte `thread`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ruft `Left.swap(Right)` auf.  
  
##  <a name="a-nameyieldfunctiona--yield"></a><a name="yield_function"></a> yield  
 Signalisiert dem Betriebssystem, andere Threads auszuführen, auch wenn der aktuelle Thread normalerweise weiterhin ausgeführt werden würde.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<thread>](../standard-library/thread.md)


