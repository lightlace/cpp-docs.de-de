---
title: "/openmp (Aktivieren der OpenMP 2.0-Unterst&#252;tzung)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/openmp"
  - "VC.Project.VCCLCompilerTool.OpenMP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/openmp (Compileroption) [C++]"
  - "-openmp (Compileroption) [C++]"
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# /openmp (Aktivieren der OpenMP 2.0-Unterst&#252;tzung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Veranlasst, dass der Compiler `#pragma` [omp](../../preprocessor/omp.md) verarbeitet.  
  
## Syntax  
  
```  
/openmp  
```  
  
## Hinweise  
 `#pragma omp` wird zur Festlegung von [Directives](../../parallel/openmp/reference/openmp-directives.md) und [Clauses](../../parallel/openmp/reference/openmp-clauses.md) verwendet.  Wenn **\/openmp** in einer Kompilierung nicht angegeben ist, werden OpenMP\-Klauseln und \-Direktiven vom Compiler ignoriert.  [OpenMP\-Funktionsaufrufe](../../parallel/openmp/reference/openmp-functions.md) werden vom Compiler verarbeitet, auch wenn **\/openmp** nicht angegeben ist.  
  
 Eine mit **\/openmp** kompilierte Anwendung, die die [Libraries](../../parallel/openmp/reference/openmp-libraries.md) verwendet, kann nur unter Windows 2000 oder späteren Betriebssystemen ausgeführt werden.  
  
 Mit **\/openmp** und **\/clr** kompilierte Anwendungen können nur in einem einzelnen Anwendungsdomänenprozess ausgeführt werden. Mehrere Anwendungsdomänen werden nicht unterstützt.  Bei Ausführung des Modulkonstruktors \(.cctor\) entdeckt dieser den mit **\/openmp** kompilierten Prozess und ob die Anwendung in eine nicht standardmäßige Laufzeit geladen wird.  Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md), [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) und [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md).  
  
 Wenn Sie versuchen, eine mit **\/openmp** und **\/clr** kompilierte Anwendung in eine nicht standardmäßige Anwendungsdomäne zu laden, wird eine <xref:System.TypeInitializationException>\-Ausnahme außerhalb des Debuggers und eine OpenMPWithMultipleAppdomainsException\-Ausnahme im Debugger ausgelöst.  
  
 Diese Ausnahmen können auch in den folgenden Situationen ausgelöst werden:  
  
-   Wenn Ihre mit **\/clr**, jedoch nicht mit **\/openmp** kompilierte Anwendung in eine nicht standardmäßige Anwendungsdomäne geladen wird und der Prozess auch eine mit **\/openmp** kompilierte Anwendung umfasst.  
  
-   Wenn Sie die **\/clr**\-Anwendung an ein Dienstprogramm wie regasm.exe \([Regasm.exe \(Assembly Registration Tool\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)\) übergeben, das die Zielassemblys der Anwendung in eine nicht standardmäßige Anwendungsdomäne lädt.  
  
 Die Codezugriffssicherheit der Common Language Runtime funktioniert nicht in OpenMP\-Bereichen.  Wenn Sie ein CLR\-Codezugriffssicherheitsattribut außerhalb eines parallelen Bereichs anwenden, ist es im parallelen Bereich nicht aktiv.  
  
 Microsoft empfiehlt, keine **\/openmp**\-Anwendungen zu schreiben, die teilweise vertrauenswürdigen Aufrufer zulassen, indem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> oder beliebige andere CLR\-Codezugriffssicherheitsattribute verwendet werden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **C\/C\+\+**.  
  
4.  Wählen Sie die Eigenschaftenseite **Sprache** aus.  
  
5.  Ändern Sie die Eigenschaft **OpenMP\-Unterstützung**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP*>.  
  
## Beispiel  
 Das folgende Beispiel zeigt einige der Auswirkungen beim Threadpool\-Start gegenüber der Verwendung von Threadpool nach dem Start.  Bei einem x64\-Single\-Core\-Dualprozessor dauert das Starten von Threadpool ca. 16 ms.  Danach benötigt Threadpool jedoch nur sehr geringe Ressourcen.  
  
 Beim Kompilieren mit **\/openmp** dauert der zweite Aufruf von test2 nie länger als beim Kompilieren mit **\/openmp\-**, da es keinen Threadpool\-Start gibt.  Bei einer Million Wiederholungen ist die **\/openmp**\-Version schneller als die **\/openmp\-**\-Version für den zweiten Aufruf von test2, bei 25 Wiederholungen verzeichnen sowohl die **\/openmp\-**\-Version als auch die **\/openmp**\-Version weniger als die Taktauflösung.  
  
 Wenn Sie daher nur eine Schleife in der Anwendung haben und sie in weniger als 15 ms ausgeführt wird \(an den ungefähren Arbeitsspeicheraufwand auf dem Computer angepasst\), ist **\/openmp** möglicherweise nicht geeignet, umfasst die Anwendung jedoch mehr, sollten Sie die Verwendung von **\/openmp** in Betracht ziehen.  
  
```  
// cpp_compiler_options_openmp.cpp  
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <windows.h>  
  
volatile DWORD dwStart;  
volatile int global = 0;  
  
double test2(int num_steps) {  
   int i;  
   global++;  
   double x, pi, sum = 0.0, step;  
  
   step = 1.0 / (double) num_steps;  
  
   #pragma omp parallel for reduction(+:sum) private(x)  
   for (i = 1; i <= num_steps; i++) {  
      x = (i - 0.5) * step;  
      sum = sum + 4.0 / (1.0 + x*x);  
   }  
  
   pi = step * sum;  
   return pi;  
}  
  
int main(int argc, char* argv[]) {  
   double   d;  
   int n = 1000000;  
  
   if (argc > 1)  
      n = atoi(argv[1]);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
}  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)