---
title: "Automatische Parallelisierung und automatische Vektorisierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Automatische Parallelisierung und automatische Vektorisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatische Parallelisierung und automatische Vektorisierung sind so konzipiert, dass automatische Leistungszuwachs für Schleifen im Code bereitgestellt wird.  
  
## Automatische Parallelisierung  
 Der Compilerschalter [\/Qpar](../build/reference/qpar-auto-parallelizer.md) aktiviert die *automatische Parallelisierung* von Schleifen im Code.  Wenn Sie dieses Flag angeben, ohne den vorhandenen Code zu ändern, wertet der Compiler den Code aus und durchsucht Schleifen, die möglicherweise von einer Parallelisierung profitieren könnten.  Da möglicherweise Schleifen gefunden werden, die nicht viel Arbeit ausführen und daher nicht von einer Parallelisierung profitiert würden, und da jede unnötige Parallelisierung die Erstellung eines Threadpools, zusätzliche Synchronisierung oder andere Prozesse auslösen kann, die die Leistung eher verlangsamen anstatt zu verbessern, ist der Compiler bei der Auswahl der Schleifen, die er parallelisiert, konservativ.  Betrachten Sie das folgende Beispiel, in dem die Obergrenze der Schleife zur Kompilierzeit nicht bekannt ist:  
  
```cpp  
  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Da `u` ein kleiner Wert sein könnte, parallelisiert der Compiler diese Schleife nicht automatisch.  Sie sollten sie dennoch parallelisierten, da Sie wissen, dass `u` immer groß ist.  Um die automatische Parallelisierung zu aktivieren, geben Sie [\#pragma loop\(hint\_parallel \(n\)\)](../preprocessor/loop.md) an, wobei `n` die Anzahl der Threads ist, über die parallelisiert werden sollen.  Im folgenden Beispiel versucht der Compiler, die Schleife über 8 Threads zu parallelisieren.  
  
```cpp  
  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Wie bei allen [Pragma\-Direktiven](../preprocessor/pragma-directives-and-the-pragma-keyword.md), wird die alternative Pragma\-Syntax `__pragma(loop(hint_parallel(n)))` ebenfalls unterstützt.  
  
 Es gibt einige Schleifen, die der Compiler nicht parallelisieren kann.  Im Folgenden ein Beispiel:  
  
```cpp  
  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 Die Funktion `upper_bound()` kann sich jedes Mal ändern, wenn sie aufgerufen wird.  Da die Obergrenze nicht bekannt sein kann, kann der Compiler eine Diagnosemeldung ausgeben, die erklärt, warum diese Schleife nicht parallelisiert werden kann.  Im folgenden Beispiel werden eine Schleife, die parallelisiert werden kann, eine Schleife, die nicht parallelisiert werden kann, die Compilersyntax, die an der Eingabeaufforderung verwendet wird, und die Compilerausgabe für jede Befehlszeilenoption dargestellt:  
  
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
  
 **cl d:\\myproject\\mylooptest.cpp \/O2 \/Qpar \/Qpar\-report:1**  
  
 löst diese Ausgabe aus:  
  
 **\-\-\- Analyzing function: void \_\_cdecl test\(void\)**   
  **d:\\myproject\\mytest.cpp\(4\) : loop parallelized**  
  
 Eine Kompilierung mit diesem Befehl:  
  
 **cl d:\\myproject\\mylooptest.cpp \/O2 \/Qpar \/Qpar\-report:2**  
  
 löst diese Ausgabe aus:  
  
 **\-\-\- Analyzing function: void \_\_cdecl test\(void\)**   
  **d:\\myproject\\mytest.cpp\(4\) : loop parallelized**   
  **d:\\myproject\\mytest.cpp\(4\) : loop not parallelized due to reason '1008'**  
  
 Beachten Sie den Unterschied in der Ausgabe zwischen den zwei verschiedenen [\/Qpar\-report \(Auto\-Parallelizer\-Berichtsebene\)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)\-Optionen.  **\/Qpar\-report:1** gibt Parallelisierungsmeldungen nur für Schleifen aus, die erfolgreich parallelisiert werden.  **\/Qpar\-report:2** gibt Parallelisierungsmeldungen für die erfolgreiche und nicht ausgeführte Schleifenparallelisierungen aus.  
  
 Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer\- and Parallelizer\-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
## Automatische Vektorisierung  
 Die automatische Vektorisierung analysiert Schleifen im Code und verwendet die Vektorregister und Anweisungen auf dem Zielcomputer, um sie, sofern möglich, auszuführen.  Damit können Sie die Leistung des Codes verbessern.  Der Compiler zielt auf die SSE2\-, AVX\- und AVX2\-Anweisungen in Intel\- oder AMD\-Prozessoren oder auf die NEON\-Anweisungen von ARM\-Prozessoren ab, gemäß dem [\/arch](../build/reference/arch-minimum-cpu-architecture.md)\-Schalter.  
  
 Die automatische Vektorisierung kann andere Anweisungen generieren, als die vom **\/arch**\-Schalter angegebenen.  Diese Anweisungen sind durch eine Laufzeitüberprüfung geschützt, um sicherzustellen, dass der Code weiterhin ordnungsgemäß ausgeführt wird.  Wenn Sie z. B. **\/arch:SSE2** kompilieren, können SSE4.2\-Anweisungen ausgegeben werden.  Eine Laufzeitüberprüfung stellt sicher, dass SSE4.2 auf dem Zielprozessor verfügbar ist, und springt zu einer Nicht\-SSE4.2\-Version der Schleife, wenn der Prozessor diese Anweisungen nicht unterstützt.  
  
 Standardmäßig ist die automatische Vektorisierung aktiviert.  Wenn Sie die Leistung des Codes bei Vektorisierung vergleichen möchten, können Sie mit [\#pragma \- loop\(no\_vector\)](../preprocessor/loop.md) die Vektorisierung für eine angegebene Schleife deaktivieren.  
  
```  
  
#pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 Wie bei allen [Pragma\-Direktiven](../preprocessor/pragma-directives-and-the-pragma-keyword.md), wird die alternative Pragma\-Syntax `__pragma(loop(no_vector))` ebenfalls unterstützt.  
  
 Wie bei der automatischen Parallelisierung können Sie die [\/Qvec\-report \(Auto\-Vectorizer\-Berichtsebene\)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)\-Befehlszeilenoption angeben, um entweder nur erfolgreich vektorisierte Schleifen – **\/Qvec\-report:1** – oder erfolgreich und nicht erfolgreich vektorisierte Schleifen – **\/Qvec\-report:2** – zu melden\).  
  
 Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer\- and Parallelizer\-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
 Ein Beispiel, in dem veranschaulicht wird, wie die Vektorisierung in der Praxis funktioniert, finden Sie im Artikel zum [Austin\-Projekt, Teil 2 von 6: Wenden von Seiten](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx).  
  
## Siehe auch  
 [Schleife](../preprocessor/loop.md)   
 [Parallele Programmierung im systemeigenen Code](http://go.microsoft.com/fwlink/?LinkId=263662)   
 [\/Qpar \(Automatische Parallelisierung\)](../build/reference/qpar-auto-parallelizer.md)   
 [\/Qpar\-report \(Auto\-Parallelizer\-Berichtsebene\)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [\/Qvec\-report \(Auto\-Vectorizer\-Berichtsebene\)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [Vectorizer\- and Parallelizer\-Meldungen](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)