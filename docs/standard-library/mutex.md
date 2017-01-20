---
title: "&lt;mutex&gt;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "<mutex>"
dev_langs: 
  - "C++"
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
caps.latest.revision: 17
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# &lt;mutex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließen Sie den Standardheader \<mutex\> zum Definieren der `mutex`\-, `recursive_mutex`\-, `timed_mutex`\- und `recursive_timed_mutex`\-Klassen ein; der Vorlagen `lock_guard` und `unique_lock` und zur Unterstützung von Typen und Funktionen, die Codebereiche für den gegenseitigen Ausschluss definieren.  
  
> [!WARNING]
>  Die STL\-Synchronisierungstypen in Visual Studio 2015 basieren auf den Windows\-Synchronisierungsprimitiven und verwenden ConcRT nicht mehr \(außer wenn Windows XP die Zielplattform ist\).  Die in \<mutex\> definierten Typen dürfen nicht mit ConcRT\-Typen oder \-Funktionen verwendet werden.  
  
## Syntax  
  
```cpp  
#include <mutex>  
```  
  
## Hinweise  
  
> [!NOTE]
>  In Code, der mithilfe von **\/clr** oder **\/clr:pure** kompiliert wird, wird dieser Header blockiert.  
  
 Die `mutex`\- und `recursive_mutex`\-Klassen sind *mutex\-Typen*.  Ein mutex\-Typ verfügt über einen Standardkonstruktor und einen Destruktor, der keine Ausnahmen auslöst.  Diese Objekte weisen Methoden auf, die gegenseitigen Ausschluss bereitstellen, wenn mehrere Threads versuchen, das gleiche Objekt zu sperren.  Ein mutex\-Typ enthält genauer gesagt die `lock`\- `try_lock`\- und `unlock`\-Methoden:  
  
-   Die `lock`\-Methode blockiert den aufrufenden Thread, bis der Thread in den Besitz von mutex gelangt.  Der Rückgabewert wird ignoriert.  
  
-   Die `try_lock`\-Methode versucht, ohne Blockierung in den Besitz von mutex zu gelangen.  Der Rückgabetyp ist in `bool` konvertierbar und weist den Wert `true` auf, wenn die Methode den Besitz erlangt, andernfalls `false`.  
  
-   Die `unlock`\-Methode gibt den Besitz von mutex von dem aufrufenden Thread frei.  
  
 Sie können mutex\-Typen als Typargumente verwenden, um die Vorlagen `lock_guard` und `unique_lock` zu instanziieren.  Sie können Objekte dieser Typen als das `Lock`\-Argument für die wait\-Memberfunktionen in der Vorlage [condition\_variable\_any](../standard-library/condition-variable-any-class.md) verwenden.  
  
 Ein *zeitgesteuerter mutex\-Typ* erfüllt die Anforderungen eines mutex\-Typs.  Darüber hinaus weist er die `try_lock_for`\- und `try_lock_until`\-Methoden auf, die mit einem Argument aufgerufen werden und einen Typ zurückgeben müssen, der in `bool` konvertiert werden kann.  Ein zeitgesteuerter mutex\-Typ kann diese Funktionen mit zusätzlichen Argumenten definieren, vorausgesetzt, dass diese zusätzlichen Argumente über Standardwerte verfügen.  
  
-   Die `try_lock_for`\-Methode muss mit einem Argument, `Rel_time`, aufgerufen werden können, dessen Typ eine Instanziierung von [chrono::duration](../standard-library/duration-class.md) ist.  Die Methode versucht, in den Besitz von mutex zu gelangen, gibt jedoch unabhängig vom Erfolg innerhalb der in `Rel_time` festgelegten Zeit einen Wert zurück.  Der Rückgabewert wird in `true` konvertiert, wenn die Methode in den Besitz von mutex gelangt; andernfalls wird der Rückgabewert in `false` konvertiert.  
  
-   Die `try_lock_until`\-Methode muss mit einem Argument, `Abs_time`, aufgerufen werden können, dessen Typ eine Instanziierung von [chrono::time\_point](../standard-library/time-point-class.md) ist.  Die Methode versucht, in den Besitz von mutex zu gelangen, gibt jedoch unabhängig vom Erfolg nicht später als innerhalb der in `Abs_time` festgelegten Zeit einen Wert zurück.  Der Rückgabewert wird in `true` konvertiert, wenn die Methode in den Besitz von mutex gelangt; andernfalls wird der Rückgabewert in `false` konvertiert.  
  
 Ein mutex\-Typ wird auch *sperrbarer Typ* genannt.  Wenn dieser keine Memberfunktion `try_lock` bereitstellt, handelt es sich bei diesem um einen *sperrbaren Basistyp*.  Ein zeitgesteuerter mutex\-Typ wird auch *zeitgesteuerter sperrbarer Typ* genannt.  
  
### Klassen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[lock\_guard\-Klasse](../standard-library/lock-guard-class.md)|Stellt eine Vorlage dar, die zum Erstellen eines Objekts instanziiert werden kann, dessen Destruktor ein `mutex`\-Objekt entsperrt.|  
|[mutex\-Klasse \(STL\)](../standard-library/mutex-class-stl.md)|Stellt einen mutex\-Typ dar.  Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss innerhalb eines Programms zu erzwingen.|  
|[recursive\_mutex\-Klasse](../standard-library/recursive-mutex-class.md)|Stellt einen mutex\-Typ dar.  Das Verhalten von aufrufenden Sperrmethoden für Objekte, die bereits gesperrt sind, ist im Gegensatz zur `mutex`\-Klasse klar definiert.|  
|[recursive\_timed\_mutex\-Klasse](../standard-library/recursive-timed-mutex-class.md)|Stellt einen zeitgesteuerten mutex\-Typ dar.  Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss mit zeitbegrenzter Blockierung innerhalb eines Programms zu erzwingen.  Im Gegensatz zu Objekten des `timed_mutex`\-Typs sind die Auswirkungen von aufrufenden Sperrmethoden für `recursive_timed_mutex`\-Objekte klar definiert.|  
|[timed\_mutex\-Klasse](../standard-library/timed-mutex-class.md)|Stellt einen zeitgesteuerten mutex\-Typ dar.  Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss mit zeitbegrenzter Blockierung innerhalb eines Programms zu erzwingen.|  
|[unique\_lock\-Klasse](../standard-library/unique-lock-class.md)|Stellt eine Vorlage dar, die zum Erstellen von Objekten instanziiert werden kann, die das Sperren und Entsperren von `mutex` verwalten.|  
  
### Funktionen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[call\_once\-Funktion](../Topic/call_once%20Function.md)|Stellt einen Mechanismus zum Aufrufen eines angegebenen aufrufbaren Objekts genau einmal während der Ausführung bereit.|  
|[lock\-Funktion](../Topic/lock%20Function.md)|Versucht, alle Argumente ohne Deadlock zu sperren.|  
  
### Strukturen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[adopt\_lock\_t\-Struktur](../standard-library/adopt-lock-t-structure.md)|Stellt einen Typ dar, der zum Definieren eines `adopt_lock`\-Elements verwendet wird.|  
|[defer\_lock\_t\-Struktur](../standard-library/defer-lock-t-structure.md)|Stellt einen Typ dar, der ein `defer_lock`\-Objekt definiert, das zum Auswählen eines überladenen Konstruktors von `unique_lock` verwendet wird.|  
|[once\_flag\-Struktur](../standard-library/once-flag-structure.md)|Stellt eine `struct` dar, die mit der `call_once`\-Vorlagenfunktion verwendet wird, damit der Initialisierungscode auch bei mehreren Ausführungsthreads nur einmal aufgerufen wird.|  
|[try\_to\_lock\_t\-Struktur](../standard-library/try-to-lock-t-structure.md)|Stellt eine `struct` dar, die ein `try_to_lock`\-Objekt definiert und zum Auswählen eines überladenen Konstruktors von `unique_lock` verwendet wird.|  
  
### Variablen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[adopt\_lock\-Variable](../Topic/adopt_lock%20Variable.md)|Stellt ein Objekt dar, das an die Konstruktoren von `lock_guard` und `unique_lock` übergeben werden kann, um anzugeben, dass das auch an den Konstruktor übergebene mutex\-Objekt gesperrt ist.|  
|[defer\_lock\-Variable](../Topic/defer_lock%20Variable.md)|Stellt ein Objekt dar, das an den Konstruktor für `unique_lock` übergeben werden kann, um anzugeben, dass der Konstruktor das an diesen übergebene mutex\-Objekt nicht sperren soll.|  
|[try\_to\_lock\-Variable](../Topic/try_to_lock%20Variable.md)|Stellt ein Objekt dar, das an den Konstruktor für `unique_lock` übergeben werden kann, um anzugeben, dass der Konstruktor das an diesen übergebene `mutex`\-Objekt ohne Blockierung entsperren soll.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)