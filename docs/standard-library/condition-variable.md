---
title: '&lt;condition_variable&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <condition_variable>
dev_langs: C++
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: baabac0a4461c659a3e70c2c26bcb971f0e1c738
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;
Definiert die Klassen [condition_variable](../standard-library/condition-variable-class.md) und [condition_variable_any](../standard-library/condition-variable-any-class.md), mit denen die Objekte erstellt werden, die auf das Eintreten einer Bedingung warten.  
  
 Für diesen Header wird "Concurrency Runtime (ConcRT)" verwendet, sodass er zusammen mit anderen ConcRT-Mechanismen verwendet werden kann. Weitere Informationen finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  In Code, der kompiliert wurde **"/ CLR"**, dieser Header blockiert.  
  
### <a name="remarks"></a>Hinweise  
 Code, der auf eine Bedingungsvariable wartet, muss auch einen `mutex` verwenden. Ein aufrufender Thread muss den `mutex` vor dem Aufrufen der Funktionen, die auf die Bedingungsvariable warten, sperren. Der `mutex` ist dann gesperrt, wenn die aufgerufene Funktion zurückgegeben wird. Die `mutex` ist nicht gesperrt, während der Thread auf das Eintreten der Bedingung wartet. Damit keine unvorhersehbaren Ergebnisse produziert werden, muss jeder Thread, der auf eine Bedingungsvariable wartet, das gleiche `mutex` Objekt verwenden.  
  
 Objekte vom Typ `condition_variable_any` können mit einem Mutex eines beliebigen Typs verwendet werden. Der Typ des verwendeten Mutex muss keine `try_lock`-Methode angeben. Objekte vom Typ `condition_variable` können ausschließlich mit einem Mutex des Typs `unique_lock<mutex>` verwendet werden. Objekte dieses Typs sind möglicherweise schneller als Objekte vom Typ `condition_variable_any<unique_lock<mutex>>`.  
  
 Sie warten auf ein Ereignis, indem Sie zuerst den Mutex sperren und anschließend eine der `wait`-Methoden auf der Bedingungsvariablen aufrufen. Der `wait`-Aufruf wird so lange gesperrt, bis ein anderer Thread die Bedingungsvariable signalisiert.  
  
 *Spurious Wakeups* treten auf, wenn die Threads, die auf die Bedingungsvariable warten, ohne geeignete Benachrichtigungen entsperrt werden. Ein solches fälschliches Aufwecken kann durch den Code, der auf das Eintreten der Bedingung wartet, erkannt werden. Dazu muss er jedoch prüfen, ob die Bedingung, auf die er wartet, tatsächlich eingetreten ist. Dies erfolgt in der Regel mithilfe einer Schleife. Verwenden Sie `wait(unique_lock<mutex>& lock, Predicate pred)`, um diese Schleife für Sie durchzuführen.  
  
```cpp  
while (condition is false)
    wait for condition variable;
```  
  
 Die `condition_variable_any`- und `condition_variable`- Klassen verfügen über drei Methoden, um auf eine Bedingung zu warten.  
  
- `wait` wartet für einen unbegrenzten Zeitraum.  
  
- `wait_until` wartet, bis einem angegebenen Zeitpunkt (`time`).  
  
- `wait_for` wartet, bis zu einer angegebenen Dauer (`time interval`).  
  
 Jede dieser Methoden verfügt über zwei überladene Versionen. Eine davon wartet einfach und kann fälschlicherweise aufwachen. Die andere verwendet ein zusätzliches Vorlagenargument, das ein Prädikat definiert. Die Methode gibt erst dann zurück, wenn das Prädikat den Wert `true` hat.  
  
 Jede Klasse verfügt auch über zwei Methoden, mit denen eine Bedingungsvariable benachrichtigt wird, dass die Bedingung den Wert `true` hat.  
  
- `notify_one` weckt einen der Threads auf, der auf die Bedingungsvariable wartet.  
  
- `notify_all` weckt alle Threads auf, die auf die Bedingungsvariable warten.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [condition_variable-Klasse](../standard-library/condition-variable-class.md)   
 [condition_variable_any-Klasse](../standard-library/condition-variable-any-class.md)
