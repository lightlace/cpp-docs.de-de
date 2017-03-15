---
title: "restrict (C++ AMP)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "cpu_CPP"
  - "amp_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Einschränkungsklausel (C++ AMP)"
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# restrict (C++ AMP)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Einschränkungsspezifizierer kann auf Funktions\- und Lambda\-Deklarationen angewendet werden.  Er erzwingt Einschränkungen für den Code in der Funktion und das Verhalten der Funktion in Anwendungen, die C\+\+ Accelerated Massive Parallelism\(C\+\+ AMP\)\-Laufzeit verwenden.  
  
> [!NOTE]
>  Informationen zum `restrict`\-Schlüsselwort, das Teil der `__declspec` Speicherklassenattribute ist, erhalten Sie unter [restrict](../cpp/restrict.md).  
  
 Die `restrict`\-Klausel nimmt folgende Formen an:  
  
|Klausel|Beschreibung|  
|-------------|------------------|  
|`restrict(cpu)`|Die Funktion kann die vollständige C\+\+\-Programmiersprache verwenden.  Es können nur andere Funktionen, die durch die Verwendung von restrict\(cpu\)\-Funktionen deklariert werden, die Funktion aufrufen.|  
|`restrict(amp)`|Die Funktion kann nur die Teilmenge der Programmiersprache C\+\+ verwenden, die mit C\+\+ AMP beschleunigt werden kann.|  
|Eine Sequenz von `restrict(cpu)` und `restrict(amp)`.|Die Funktion muss den Einschränkungen von `restrict(cpu)` und `restrict(amp)` folgen.  Die Funktion kann von Funktionen aufgerufen werden, die durch die Verwendung von `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` oder `restrict(amp, cpu)` deklariert werden.<br /><br /> Das Formular `restrict(A) restrict(B)` kann als `restrict(A,B)` geschrieben werden.|  
  
## Hinweise  
 Das Schlüsselwort `restrict` ist ein Kontextschlüsselwort.  Die Einschränkungsspezifizierer, `cpu` und `amp` sind keine reservierten Wörter.  Die Liste der Spezifizierer ist nicht erweiterbar.  Eine Funktion, die keine `restrict`\-Klausel enthält, ist dasselbe wie eine Funktion, die über `restrict(cpu)`\-Klausel verfügt.  
  
 Eine Funktion, die über die `restrict(amp)`\-Klausel verfügt, hat folgende Einschränkungen:  
  
-   Die Funktion kann nur Funktionen aufrufen, die die `restrict(amp)`\-Klausel enthalten.  
  
-   Die Funktion muss inlinable sein.  
  
-   Die Funktion kann nur `int`, `unsigned int`, `float` und `double`\-Variablen sowie Klassen und Strukturen deklarieren, die nur diese Typen enthalten.  `bool` ist ebenfalls zulässig, muss jedoch mit 4 Bytes ausgerichtet sein, wenn Sie es in einem Verbundtyp verwenden.  
  
-   Lambda\-Funktionen können nicht als Verweis erfassten und können keine Zeiger erfassen.  
  
-   Verweise und Einzeldereferenzierungszeiger werden nur als lokale Variablen, Funktionsargumente und Rückgabetypen unterstützt.  
  
-   Folgendes ist nicht zulässig:  
  
    -   Rekursion.  
  
    -   Variablen, die mit dem [volatile](../cpp/volatile-cpp.md)\-Schlüsselwort deklariert sind.  
  
    -   Virtuelle Funktionen.  
  
    -   Zeiger auf Funktionen.  
  
    -   Zeiger auf die Memberfunktionen.  
  
    -   Zeiger in Strukturen.  
  
    -   Zeiger auf Zeiger.  
  
    -   `goto`\-Anweisungen.  
  
    -   Anweisungen mit Bezeichnung.  
  
    -   `try`\-, `catch`\- oder `throw`\-Anweisungen.  
  
    -   Globale Variablen.  
  
    -   Statische Variablen.  Verwenden Sie stattdessen [tile\_static\-Schlüsselwort](../cpp/tile-static-keyword.md).  
  
    -   `dynamic_cast`\-Umwandlungen.  
  
    -   Der Operator `typeid`.  
  
    -   ASM\-Deklarationen.  
  
    -   Varargs.  
  
 Eine Erläuterung der Funktionseinschränkungen finden Sie unter [restrict\(amp\)\-Einschränkungen](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der `restrict(amp)`\-Klausel veranschaulicht.  
  
```  
  
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
  
}  
```  
  
## Siehe auch  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)