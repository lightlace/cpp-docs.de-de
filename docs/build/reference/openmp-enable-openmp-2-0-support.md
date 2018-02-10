---
title: "-Openmp (Aktivieren der OpenMP 2.0-Unterstützung) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
dev_langs:
- C++
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8217a901f071f50dbd2d7dfcbffccf4014a9444
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (Aktivieren der OpenMP 2.0-Unterstützung)
Bewirkt, dass der Compiler verarbeiten `#pragma` [Omp](../../preprocessor/omp.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
/openmp  
```  
  
## <a name="remarks"></a>Hinweise  
 `#pragma omp`Dient zum angeben [Direktiven](../../parallel/openmp/reference/openmp-directives.md) und [Klauseln](../../parallel/openmp/reference/openmp-clauses.md). Wenn **/OpenMP** ist nicht in einer Kompilierung angegeben, OpenMP-Klauseln und Direktiven vom Compiler ignoriert. [OpenMP-Funktion](../../parallel/openmp/reference/openmp-functions.md) Aufrufe werden verarbeitet, indem die Compiler, selbst wenn **/OpenMP** nicht angegeben wird.  
  
 Anwendungen mit kompiliert **/OpenMP** und **"/ CLR"** können nur in einer einzelnen Domäne Anwendungsprozess ausgeführt werden, mehreren Anwendungsdomänen werden nicht unterstützt. D. h. bei der Modulkonstruktor (".cctor") ausgeführt wird, es erkennt der Prozess mit kompiliert **/OpenMP** und wenn die Anwendung in eine nicht standardmäßige Laufzeit geladen wird. Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md), [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md), und [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md).  
  
 Wenn Sie versuchen, eine Anwendung mit kompiliert laden **/OpenMP** und **"/ CLR"** in eine nicht standardmäßige Anwendungsdomäne eine <xref:System.TypeInitializationException> Ausnahme außerhalb des Debuggers und einer OpenMPWithMultipleAppdomainsException Ausnahme wird im Debugger ausgelöst werden.  
  
 Diese Ausnahmen können auch in den folgenden Situationen ausgelöst werden:  
  
-   Wenn Ihre Anwendung mit kompiliert **"/ CLR"**, jedoch nicht mit **/OpenMP**, geladen wird in eine nicht standardmäßige Anwendungsdomäne, in dem der Prozess für eine Anwendung enthält, die mit kompiliert wurde **/ OpenMP**.  
  
-   Wenn Sie übergeben Ihr **"/ CLR"** Anwendung mit einem Hilfsprogramm, z. B. regasm.exe ([Regasm.exe (Assembly Registration-Tool)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), die die Zielassemblys in eine nicht standardmäßige Anwendungsdomäne lädt.  
  
 Die common Language Runtime-Codezugriffssicherheit funktioniert nicht in OpenMP-Regionen. Wenn Sie außerhalb eines parallelen Bereichs ein CLR Code Access Security-Attribut anwenden, wird nicht es in den parallelen Bereich wirksam sein.  
  
 Microsoft empfiehlt, dass Sie keine schreiben **/OpenMP** Anwendungen, die ermöglicht das teilweise vertrauenswürdigen Aufrufern, mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, oder eine beliebige CLR Codezugriffs-Sicherheitsattribute.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **C/C++-** Knoten.  
  
4.  Wählen Sie die **Sprache** Eigenschaftenseite.  
  
5.  Ändern der **OpenMP-Unterstützung** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einige der Auswirkungen der Threadpool-Start im Vergleich zu den Threadpool verwendet werden, nachdem es gestartet. Vorausgesetzt, ein X64, single-Core akzeptiert Dualprozessor Threadpool ungefähr 16 ms hochgefahren ist. Danach gibt es ist sehr wenig Kosten für den Threadpool.  
  
 Beim Kompilieren mit **/OpenMP**, der zweite Aufruf von test2 führt nie länger als beim Kompilieren mit **/openmp-**, da es keinen Threadpool-Start. Bei einer Million Iterationen der **/OpenMP** Version ist schneller als die **/openmp-** Version für den zweiten Aufruf von test2 sowie auf 25 Iterationen **/openmp-** und **/OpenMP** kleiner als die Granularität Uhr Versionen registrieren.  
  
 Ja, wenn Sie nur eine Schleife in der Anwendung und in weniger als 15ms (angepasst für den ungefähren Aufwand auf dem Computer), ausgeführt wird **/OpenMP** möglicherweise nicht geeignet, wenn es mehr als die, die verwendet wird, sollten Sie in Betracht **/OpenMP**.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)