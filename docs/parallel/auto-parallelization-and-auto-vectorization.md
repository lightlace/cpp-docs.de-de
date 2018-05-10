---
title: Automatische Parallelisierung und automatische Vektorisierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1ec19065647f78b4d9b2665003c0aa3a2795ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Automatische Parallelisierung und automatische Vektorisierung
Automatische Parallelisierung und automatische Vektorisierung sind so konzipiert, dass automatische Leistungszuwachs für Schleifen im Code bereitgestellt wird.  
  
## <a name="auto-parallelizer"></a>Automatische Parallelisierung  
 Die [/Qpar](../build/reference/qpar-auto-parallelizer.md) Compilerschalter ermöglicht *automatische Parallelisierung* von Schleifen im Code. Wenn Sie dieses Flag angeben, ohne den vorhandenen Code zu ändern, wertet der Compiler den Code aus und durchsucht Schleifen, die möglicherweise von einer Parallelisierung profitieren könnten. Da möglicherweise Schleifen gefunden werden, die nicht viel Arbeit ausführen und daher nicht von einer Parallelisierung profitiert würden, und da jede unnötige Parallelisierung die Erstellung eines Threadpools, zusätzliche Synchronisierung oder andere Prozesse auslösen kann, die die Leistung eher verlangsamen anstatt zu verbessern, ist der Compiler bei der Auswahl der Schleifen, die er parallelisiert, konservativ. Betrachten Sie das folgende Beispiel, in dem die Obergrenze der Schleife zur Kompilierzeit nicht bekannt ist:  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Da `u` ein kleiner Wert sein könnte, parallelisiert der Compiler diese Schleife nicht automatisch. Sie sollten sie dennoch parallelisierten, da Sie wissen, dass `u` immer groß ist. Um die automatische Parallelisierung zu aktivieren, geben [#pragma loop(hint_parallel(n))](../preprocessor/loop.md), wobei `n` ist die Anzahl der Threads an, die über die parallelisiert. Im folgenden Beispiel versucht der Compiler, die Schleife über 8 Threads zu parallelisieren.  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Wie bei allen [pragma-Direktiven](../preprocessor/pragma-directives-and-the-pragma-keyword.md), die alternative Pragma-Syntax `__pragma(loop(hint_parallel(n)))` wird ebenfalls unterstützt.  
  
 Es gibt einige Schleifen, die der Compiler nicht parallelisieren kann. Im Folgenden ein Beispiel:  
  
```cpp  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 Die Funktion `upper_bound()` kann sich jedes Mal ändern, wenn sie aufgerufen wird. Da die Obergrenze nicht bekannt sein kann, kann der Compiler eine Diagnosemeldung ausgeben, die erklärt, warum diese Schleife nicht parallelisiert werden kann. Im folgenden Beispiel werden eine Schleife, die parallelisiert werden kann, eine Schleife, die nicht parallelisiert werden kann, die Compilersyntax, die an der Eingabeaufforderung verwendet wird, und die Compilerausgabe für jede Befehlszeilenoption dargestellt:  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 Eine Kompilierung mit diesem Befehl:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-Bericht: 1**  
  
 löst diese Ausgabe aus:  
  
 **---Funktion analysieren: "void" __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): Schleife parallelisiert**  
  
 Eine Kompilierung mit diesem Befehl:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-Bericht: 2**  
  
 löst diese Ausgabe aus:  
  
 **---Funktion analysieren: "void" __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): Schleife parallelisiert**   
 **d:\myproject\mytest.cpp(4): Schleife nicht parallelisierte wegen der Ursache "1008"**  
  
 Beachten Sie den Unterschied in der Ausgabe zwischen den beiden anderen [/qpar-Report (Auto-Parallelisierer Reporting Stufe)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) Optionen. **/ Qpar-Bericht: 1-** gibt parallelisierungsmeldungen nur für Schleifen an, die erfolgreich parallelisiert werden. **/ Qpar-Bericht: 2** gibt parallelisierungsmeldungen für beide Parallelizations erfolgreiche sowie nicht erfolgreiche Schleife.  
  
 Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
## <a name="auto-vectorizer"></a>Automatische Vektorisierung  
 Die automatische Vektorisierung analysiert Schleifen im Code und verwendet die Vektorregister und Anweisungen auf dem Zielcomputer, um sie, sofern möglich, auszuführen. Damit können Sie die Leistung des Codes verbessern. Der Compiler ausgerichtet ist, die SSE2-, AVX- und AVX2-Anweisungen in Intel- oder AMD-Prozessoren oder die NEON-Anweisungen von ARM-Prozessoren gemäß der [/arch](../build/reference/arch-minimum-cpu-architecture.md) wechseln.  
  
 Die automatische Vektorisierung kann andere Anweisungen generieren, als die **/arch** wechseln. Diese Anweisungen sind durch eine Laufzeitüberprüfung geschützt, um sicherzustellen, dass der Code weiterhin ordnungsgemäß ausgeführt wird. Wenn Sie z. B. Kompilieren **SSE2**, SSE4. 2-Anweisungen ausgegeben werden. Eine Laufzeitüberprüfung stellt sicher, dass SSE4.2 auf dem Zielprozessor verfügbar ist, und springt zu einer Nicht-SSE4.2-Version der Schleife, wenn der Prozessor diese Anweisungen nicht unterstützt.  
  
 Standardmäßig ist die automatische Vektorisierung aktiviert. Wenn Sie die Leistung des Codes bei Vektorisierung vergleichen möchten, können Sie [#pragma-loop(no_vector)](../preprocessor/loop.md) Vektorisierung für eine angegebene Schleife deaktivieren.  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 Wie bei allen [pragma-Direktiven](../preprocessor/pragma-directives-and-the-pragma-keyword.md), die alternative Pragma-Syntax `__pragma(loop(no_vector))` wird ebenfalls unterstützt.  
  
 Wie mit der automatischen Parallelisierung können Sie angeben, können die [/Qvec-report (Auto-Vektorisierer Reporting Stufe)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) Befehlszeilenoption entweder erfolgreich melden vektorisierte Schleifen nur –**/Qvec-Bericht: 1-**– oder sowohl erfolgreich und nicht erfolgreich vektorisierte Schleifen –**/Qvec-Bericht: 2**).  
  
 Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
 Ein Beispiel dafür, wie die vektorisierer in der Praxis funktioniert, finden Sie unter [Projekt Austin Teil 2 von 6: Seite gewelltem](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Schleife](../preprocessor/loop.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?linkid=263662)   
 [/ Qpar (automatische Parallelisierung)](../build/reference/qpar-auto-parallelizer.md)   
 [/ Qpar-Report-(Auto-Parallelizer-Berichtsebene)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/ Qvec-Report-(Auto-Vektorisierer Berichtsebene)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [Vectorizer- und Parallelizer-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)