---
title: '&lt;future&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 12
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 3c603ac75955c057cfba009494a9a430fd987a69
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt;-Funktionen
||||  
|-|-|-|  
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|  
|[swap](#swap)|[yield](#yield)|  
  
##  <a name="get_id"></a> get_id  
 Weist den aktuellen Ausführungsthread eindeutig aus.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt vom Typ [Thread:: ID](../standard-library/thread-class.md), das den aktuellen Ausführungsthread eindeutig ausweist.  
  
##  <a name="sleep_for"></a> sleep_for  
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
  
##  <a name="sleep_until"></a> sleep_until  
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
  
##  <a name="swap"></a> swap  
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
  
##  <a name="yield"></a> yield  
 Signalisiert dem Betriebssystem, andere Threads auszuführen, auch wenn der aktuelle Thread normalerweise weiterhin ausgeführt werden würde.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<thread>](../standard-library/thread.md)


