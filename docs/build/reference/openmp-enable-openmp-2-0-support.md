---
title: / OpenMP (Aktivieren der OpenMP-Unterstützung)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: caa06d89c590abd2b3a74a5a6b118d6ba4acd910
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320213"
---
# <a name="openmp-enable-openmp-support"></a>/ OpenMP (Aktivieren der OpenMP-Unterstützung)

Bewirkt, dass der Compiler verarbeiten [ `#pragma omp` ](../../preprocessor/omp.md) Direktiven zur Unterstützung von OpenMP.

## <a name="syntax"></a>Syntax

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__experimental__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>Hinweise

`#pragma omp` Dient zur Angabe [Direktiven](../../parallel/openmp/reference/openmp-directives.md) und [Klauseln](../../parallel/openmp/reference/openmp-clauses.md). Wenn **/OpenMP** ist nicht in einer Kompilierung angegeben, der Compiler ignoriert OpenMP-Klauseln und -Direktiven. [OpenMP-Funktion](../../parallel/openmp/reference/openmp-functions.md) Aufrufe werden verarbeitet, die Compiler selbst dann durch **/OpenMP** nicht angegeben ist.

::: moniker range=">= vs-2019"

Die C++ -Compiler unterstützt derzeit die OpenMP 2.0-Standards. Visual Studio-2019 bietet jedoch nun auch SIMD-Funktionen. Um SIMD zu verwenden, kompilieren Sie mithilfe der **/OpenMP: experimentelle** Option. Diese Option ermöglicht sowohl die üblichen OpenMP-Funktionen sowie zusätzliche OpenMP SIMD Funktionen nicht verfügbar bei Verwendung der **/OpenMP** wechseln.

::: moniker-end

Anwendungen, die kompiliert werden, indem beide **/OpenMP** und **"/ CLR"** kann nur in einer einzelnen Domäne Anwendungsprozess ausgeführt werden. Mehrere Anwendungsdomänen werden nicht unterstützt. D. h., wenn der Modulkonstruktor (`.cctor`) wird ausgeführt, sie erkennt, ob der Prozess mit kompiliert wird **/OpenMP**, und wenn die app in eine nicht standardmäßige-Laufzeit geladen wird. Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md), [/CLR (Common Language Runtime Compilation)](clr-common-language-runtime-compilation.md), und [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md).

Wenn Sie versuchen, laden eine app, die kompiliert wird, mit **/OpenMP** und **"/ CLR"** in eine nicht standardmäßige Anwendungsdomäne eine <xref:System.TypeInitializationException> ausgelöster Ausnahme außerhalb des Debuggers und ein `OpenMPWithMultipleAppdomainsException` Ausnahme wird im Debugger ausgelöst werden.

Diese Ausnahmen können auch in den folgenden Situationen ausgelöst werden:

- Wenn Ihre Anwendung kompiliert wird, mit **"/ CLR"** aber nicht **/OpenMP**, wird in eine nicht standardmäßige Anwendungsdomäne, in dem der Prozess umfasst eine app mithilfe von kompiliert geladen   **/OpenMP**.

- Wenn Sie übergeben Ihrer **"/ CLR"** app mit einem Hilfsprogramm, wie z. B. [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), die Zielassemblys in eine nicht standardmäßige Anwendungsdomäne lädt.

Die common Language Runtime-Codezugriffssicherheit funktioniert nicht in OpenMP-Regionen. Wenn Sie ein CLR-Code Access Security Attribut außerhalb eines parallelen Bereichs anwenden, nicht es in den parallelen Bereich wirksam.

Microsoft empfiehlt, dass Sie schreiben **/OpenMP** apps, mit denen teilweise vertrauenswürdigen Aufrufern. Verwenden Sie keine <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, oder alle CLR Codezugriffs-Sicherheitsattribute.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften** > **C /C++** > **Sprache** Eigenschaftenseite.

1. Ändern der **OpenMP-Unterstützung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt einige der Auswirkungen von Thread-Pool-Start im Vergleich zur Verwendung des Threadpools, nachdem es gestartet wurde. X X64, single-Core dual-Prozessor vorausgesetzt, nimmt Threadpool der Warteschleife hinzu ca. 16 ms gestartet wird. Danach ist es wenig zusätzliche für den Threadpool Kosten an.

Beim Kompilieren mit **/OpenMP**, der zweite Aufruf von test2 nicht ausgeführt wird, nicht mehr als beim Kompilieren mit **/openmp-**, da es keinen Thread Pool Start. Auf eine Million Iterationen die **/OpenMP** Version ist schneller als die **/openmp-** Version für den zweiten Aufruf von test2. Auf 25 Iterationen beide **/openmp-** und **/OpenMP** kleiner als die Granularität der Uhr Versionen registrieren.

Wenn Sie nur eine Schleife in Ihrer Anwendung und Ausführung in weniger als 15 ms (angepasst für den ungefähren Aufwand auf Ihrem Computer), **/OpenMP** eventuell nicht möglich. Wenn er höher ist, sollten Sie erwägen **/OpenMP**.

```cpp
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

[MSVC-Compiler-Optionen](compiler-options.md) \
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md) \
[OpenMP in MSVC](../../parallel/openmp/openmp-in-visual-cpp.md)
