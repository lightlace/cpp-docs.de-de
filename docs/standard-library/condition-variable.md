---
title: "&lt;condition_variable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<condition_variable>"
dev_langs: 
  - "C++"
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;condition_variable&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Klassen [condition\_variable](../standard-library/condition-variable-class.md) und [condition\_variable\_any](../standard-library/condition-variable-any-class.md), die verwendet werden, um Objekte zu erstellen, die auf eine Bedingung warten, um ausgeführt zu werden.  
  
 Für diesen Header wird "Concurrency Runtime \(ConcRT\)" verwendet, sodass er zusammen mit anderen ConcRT\-Mechanismen verwendet werden kann.  Weitere Informationen über ConcRT finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).  
  
## Syntax  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  In Code, der mithilfe von **\/clr** oder **\/clr:pure** kompiliert wird, wird dieser Header blockiert.  
  
### Hinweise  
 Code, dass auf eine Bedingungsvariable `mutex` verwenden müssen.  Ein aufrufenden Thread muss `mutex` sperren, bevor er die Funktionen aufgerufen, die auf die Bedingungsvariable warten.  `mutex` wird dann gesperrt, wenn die aufgerufene Funktion zurückkehrt.  `mutex` wird nicht gesperrt, während der Thread auf die Bedingung true wartet, um zu werden.  Damit es keine unvorhersehbaren Ergebnissen gibt, jeder Thread, dass auf eine Bedingungsvariable das gleiche `mutex`\-Objekt verwenden müssen.  
  
 Objekte des Typs `condition_variable_any` können mit einem Mutex eines Typs verwendet werden.  Der Typ des Mutex, der verwendet wird, muss die `try_lock`\-Methode nicht bereitstellen.  Objekte des Typs `condition_variable` können mit einem Mutex des Typs `unique_lock<mutex>` nur verwendet werden.  Objekte dieses Typs sind möglicherweise schneller als Objekte vom Typ `condition_variable_any<unique_lock<mutex>>`.  
  
 Um auf Ereignisse warten, sperren Sie zuerst der Mutex, und rufen Sie dann eine der Methoden `wait` auf der Bedingungsvariable auf.  Die `wait` Aufruf wird blockiert auf einen anderen Thread signalisiert der Bedingungsvariable.  
  
 *Unechtes Wecken* tritt auf, wenn Threads, die Bedingungsvariablen wartende sind, ohne dass entsprechende Benachrichtigungen nicht blockiert werden.  Um solche unechte Wecken zu erkennen, codieren Sie Wartungsarbeiten dass eine Bedingung erfüllt werden ob Bedingung explizit überprüfen sollten wenn die Coderückgaben von einem Wartevorgang arbeiten.  Dies wird normalerweise durchgeführt, indem eine Schleife verwendet; Sie können `wait(unique_lock<mutex>& lock, Predicate pred)` verwenden, um diese Schleife für Sie ausgeführt.  
  
```cpp  
while (condition is false)  
    wait for condition variable;  
```  
  
 `condition_variable_any` und `condition_variable` werden jeweils über drei Methoden, die auf eine Bedingung warten.  
  
-   `wait` Wartung einen unendlichen Zeitraum.  
  
-   `wait_until` wartet auf einen angegebenen `time`.  
  
-   Wartet `wait_for` einen angegebenen `time interval`.  
  
 Jede dieser Methoden verfügt über zwei überladene Versionen.  Ein gerade wartet und kann unecht aufwachen.  Der andere akzeptiert ein zusätzliches Vorlagenargument, das ein Prädikat definiert.  Die Methode wird erst zurückgegeben, wenn das Prädikat `true` ist.  
  
 Jede Klasse besitzt ebenfalls zwei Methoden, die verwendet werden, um eine Bedingungsvariable zu benachrichtigen, dass die Bedingung `true` ist.  
  
-   `notify_one` wird einem der Threads auf, der die Bedingungsvariable wartet.  
  
-   `notify_all` wird alle Threads, die die Bedingungsvariable warten.  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [condition\_variable\-Klasse](../standard-library/condition-variable-class.md)   
 [condition\_variable\_any\-Klasse](../standard-library/condition-variable-any-class.md)   
 [cv\_status\-Enumeration](../Topic/cv_status%20Enumeration.md)