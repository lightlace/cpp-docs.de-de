---
title: "einschränken (C++-AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60ac40e2cb64c307574d14c1f7cc7a5290c740ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
Der Einschränkungsspezifizierer kann auf Funktions- und Lambda-Deklarationen angewendet werden. Er erzwingt Einschränkungen für den Code in der Funktion und das Verhalten der Funktion in Anwendungen, die C++ Accelerated Massive Parallelism(C++ AMP)-Laufzeit verwenden.  
  
> [!NOTE]
>  Informationen zu den `restrict` Schlüsselwort, das Teil ist die `__declspec` speicherklassenattribute, finden Sie unter [beschränken](../cpp/restrict.md).  
  
 Die `restrict`-Klausel nimmt folgende Formen an:  
  
|Klausel|Beschreibung|  
|------------|-----------------|  
|`restrict(cpu)`|Die Funktion kann die vollständige C++-Programmiersprache verwenden. Es können nur andere Funktionen, die durch die Verwendung von restrict(cpu)-Funktionen deklariert werden, die Funktion aufrufen.|  
|`restrict(amp)`|Die Funktion kann nur die Teilmenge der Programmiersprache C++ verwenden, die mit C++ AMP beschleunigt werden kann.|  
|Eine Sequenz von `restrict(cpu)` und `restrict(amp)`.|Die Funktion muss den Einschränkungen von `restrict(cpu)` und `restrict(amp)` folgen. Die Funktion kann von Funktionen aufgerufen werden, die durch die Verwendung von `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` oder `restrict(amp, cpu)` deklariert werden.<br /><br /> Das Formular `restrict(A) restrict(B)` kann als `restrict(A,B)` geschrieben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort `restrict` ist ein Kontextschlüsselwort. Die Einschränkungsspezifizierer, `cpu` und `amp` sind keine reservierten Wörter. Die Liste der Spezifizierer ist nicht erweiterbar. Eine Funktion, die keine `restrict`-Klausel enthält, ist dasselbe wie eine Funktion, die über `restrict(cpu)`-Klausel verfügt.  
  
 Eine Funktion, die über die `restrict(amp)`-Klausel verfügt, hat folgende Einschränkungen:  
  
-   Die Funktion kann nur Funktionen aufrufen, die die `restrict(amp)`-Klausel enthalten.  
  
-   Die Funktion muss inlinable sein.  
  
-   Die Funktion kann nur `int`, `unsigned int`, `float` und `double`-Variablen sowie Klassen und Strukturen deklarieren, die nur diese Typen enthalten. `bool` ist ebenfalls zulässig, muss jedoch mit 4 Bytes ausgerichtet sein, wenn Sie es in einem Verbundtyp verwenden.  
  
-   Lambda-Funktionen können nicht als Verweis erfassten und können keine Zeiger erfassen.  
  
-   Verweise und Einzeldereferenzierungszeiger werden nur als lokale Variablen, Funktionsargumente und Rückgabetypen unterstützt.  
  
-   Folgendes ist nicht zulässig:  
  
    -   Rekursion.  
  
    -   Variablen, die mit der [volatile](../cpp/volatile-cpp.md) Schlüsselwort.  
  
    -   Virtuelle Funktionen.  
  
    -   Zeiger auf Funktionen.  
  
    -   Zeiger auf die Memberfunktionen.  
  
    -   Zeiger in Strukturen.  
  
    -   Zeiger auf Zeiger.  
  
    -   `goto`-Anweisungen.  
  
    -   Anweisungen mit Bezeichnung.  
  
    -   `try`-, `catch`- oder `throw`-Anweisungen.  
  
    -   Globale Variablen.  
  
    -   Statische Variablen. Verwendung [Tile_static-Schlüsselwort](../cpp/tile-static-keyword.md) stattdessen.  
  
    -   `dynamic_cast`-Umwandlungen.  
  
    -   Der Operator `typeid`.  
  
    -   ASM-Deklarationen.  
  
    -   Varargs.  
  
 Eine Erläuterung der Einschränkungen der Funktion, finden Sie unter [restrict(amp) Einschränkungen](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `restrict(amp)`Klausel.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)