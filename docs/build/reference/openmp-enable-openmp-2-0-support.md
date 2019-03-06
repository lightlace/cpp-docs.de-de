---
title: /openmp (Aktivieren der OpenMP 2.0-Unterstützung)
ms.date: 11/04/2016
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: bea51c7af41df666fd441555daa0d8d8387377ac
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414134"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (Aktivieren der OpenMP 2.0-Unterstützung)

Bewirkt, dass der Compiler verarbeiten `#pragma` [Omp](../../preprocessor/omp.md).

## <a name="syntax"></a>Syntax

```
/openmp
```

## <a name="remarks"></a>Hinweise

`#pragma omp` Dient zur Angabe [Direktiven](../../parallel/openmp/reference/openmp-directives.md) und [Klauseln](../../parallel/openmp/reference/openmp-clauses.md). Wenn **/OpenMP** nicht angegeben ist in einer Kompilierung der Compiler ignoriert OpenMP-Klauseln und -Direktiven. [OpenMP-Funktion](../../parallel/openmp/reference/openmp-functions.md) Aufrufe werden verarbeitet, die Compiler selbst dann durch **/OpenMP** nicht angegeben ist.

Anwendungen mit kompiliert **/OpenMP** und **"/ CLR"** kann nur in einer einzelnen Domäne Anwendungsprozess ausgeführt werden, mehrere Anwendungsdomänen werden nicht unterstützt. D. h. wenn die Modulkonstruktor (.cctor) ausgeführt wird, erkennt der Prozess wird mit kompiliert **/OpenMP** und wenn die Anwendung in eine nicht standardmäßige-Laufzeit geladen wird. Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md), [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md), und [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md).

Wenn Sie versuchen, eine Anwendung mit kompiliert laden **/OpenMP** und **"/ CLR"** in eine nicht standardmäßige Anwendungsdomäne eine <xref:System.TypeInitializationException> Ausnahme außerhalb des Debuggers ausgelöst und ein OpenMPWithMultipleAppdomainsException Ausnahme wird im Debugger ausgelöst werden.

Diese Ausnahmen können auch in den folgenden Situationen ausgelöst werden:

- Wenn Ihre Anwendung mit kompiliert **"/ CLR"**, jedoch nicht mit **/OpenMP**, geladen wird in eine nicht standardmäßige Anwendungsdomäne, in dem der Prozess für eine Anwendung enthält, die mit kompiliert wurde **/ OpenMP**.

- Wenn Sie übergeben Ihrer **"/ CLR"** Anwendung mit einem Hilfsprogramm, z. B. regasm.exe ([Regasm.exe (Assembly Registration-Tool)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), die Zielassemblys in eine nicht standardmäßige Anwendungsdomäne lädt.

Die common Language Runtime-Codezugriffssicherheit funktioniert nicht in OpenMP-Regionen. Wenn Sie ein CLR-Code Access Security Attribut außerhalb eines parallelen Bereichs anwenden, nicht es in den parallelen Bereich wirksam.

Microsoft empfiehlt, dass Sie keine schreiben **/OpenMP** Anwendungen, die ermöglicht das teilweise vertrauenswürdigen Aufrufern, mithilfe von <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, oder alle CLR Codezugriffs-Sicherheitsattribute.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **C/C++-** Knoten.

1. Wählen Sie die **Sprache** Eigenschaftenseite.

1. Ändern der **OpenMP-Unterstützung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt einige der Auswirkungen von Threadpool-Start im Vergleich zur Verwendung des Threadpools, nachdem es gestartet wird. X X64, einzigen Kern ausgeführt Wenn, dauert Dualprozessor Threadpool ca. 16 ms starten. Nach, die jedoch besteht sehr geringen Kosten für den Threadpool.

Beim Kompilieren mit **/OpenMP**, der zweite Aufruf von test2 nicht ausgeführt wird, nicht mehr als beim Kompilieren mit **/openmp-**, da es keinen Threadpool-Start. Auf eine Million Iterationen der **/OpenMP** Version ist schneller als die **/openmp-** Version für den zweiten Aufruf von test2, und klicken Sie auf 25 Iterationen **/openmp-** und **/OpenMP** kleiner als die Granularität der Uhr Versionen registrieren.

Wenn Sie nur eine Schleife in Ihrer Anwendung haben und sie ausgeführt wird, in weniger als 15ms (angepasst für den ungefähren Aufwand auf Ihrem Computer), **/OpenMP** eventuell nicht möglich, wenn es mehr als das verwendet wird, sollten Sie für den Einsatz von **/OpenMP**.

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

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
