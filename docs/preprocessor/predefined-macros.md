---
title: Vordefinierte Makros
ms.custom: update_every_version
ms.date: 04/05/2019
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
- _CHAR_UNSIGNED
- __CLR_VER
- _CONTROL_FLOW_GUARD
- __COUNTER__
- __cplusplus
- __cplusplus_cli
- __cplusplus_winrt
- _CPPRTTI
- _CPPUNWIND
- __DATE__
- _DEBUG
- _DLL
- __FILE__
- __FUNCDNAME__
- __FUNCSIG__
- __FUNCTION__
- _INTEGRAL_MAX_BITS
- _ISO_VOLATILE
- _KERNEL_MODE
- __LINE__
- _M_AMD64
- _M_ARM
- _M_ARM_ARMV7VE
- _M_ARM_FP
- _M_ARM64
- _M_CEE
- _M_CEE_PURE
- _M_CEE_SAFE
- _M_FP_EXCEPT
- _M_FP_FAST
- _M_FP_PRECISE
- _M_FP_STRICT
- _M_IX86
- _M_IX86_FP
- _M_X64
- _MANAGED
- _MFC_VER
- _MSC_BUILD
- _MSC_EXTENSIONS
- _MSC_FULL_VER
- _MSC_VER
- _MSVC_LANG
- __MSVC_RUNTIME_CHECKS
- _MT
- _NATIVE_WCHAR_T_DEFINED
- _NO_SIZED_DEALLOCATION
- _OPENMP
- _PREFAST_
- _RESUMABLE_FUNCTIONS_SUPPORTED
- _RTC_CONVERSION_CHECKS_ENABLED
- __STDC__
- __STDC_HOSTED__
- __STDCPP_THREADS__
- __TIME__
- __TIMESTAMP__
- __VA_ARGS__
- _VC_NODEFAULTLIB
- _WCHAR_T_DEFINED
- _WIN32
- _WIN64
- _WINRT_DLL
- __func__
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- _ATL_VER macro
- __ATOM__ macro
- __AVX__ macro
- __AVX2__ macro
- _CHAR_UNSIGNED macro
- __CLR_VER macro
- _CONTROL_FLOW_GUARD macro
- __COUNTER__ macro
- __cplusplus macro
- __cplusplus_cli macro
- __cplusplus_winrt macro
- _CPPRTTI macro
- _CPPUNWIND macro
- __DATE__ macro
- _DEBUG macro
- _DLL macro
- __FILE__ macro
- __FUNCDNAME__ macro
- __FUNCSIG__ macro
- __FUNCTION__ macro
- _INTEGRAL_MAX_BITS macro
- _ISO_VOLATILE macro
- _KERNEL_MODE macro
- __LINE__ macro
- _M_AMD64 macro
- _M_ARM macro
- _M_ARM_ARMV7VE macro
- _M_ARM_FP macro
- _M_ARM64 macro
- _M_CEE macro
- _M_CEE_PURE macro
- _M_CEE_SAFE macro
- _M_FP_EXCEPT macro
- _M_FP_FAST macro
- _M_FP_PRECISE macro
- _M_FP_STRICT macro
- _M_IX86 macro
- _M_IX86_FP macro
- _M_X64 macro
- _MANAGED macro
- _MFC_VER macro
- _MSC_BUILD macro
- _MSC_EXTENSIONS macro
- _MSC_FULL_VER macro
- _MSC_VER macro
- _MSVC_LANG macro
- __MSVC_RUNTIME_CHECKS macro
- _MT macro
- _NATIVE_WCHAR_T_DEFINED macro
- _NO_SIZED_DEALLOCATION macro
- _OPENMP macro
- _PREFAST_ macro
- _RESUMABLE_FUNCTIONS_SUPPORTED macro
- _RTC_CONVERSION_CHECKS_ENABLED macro
- __STDC__ macro
- __STDC_HOSTED__ macro
- __STDCPP_THREADS__ macro
- __TIME__ macro
- __TIMESTAMP__ macro
- __VA_ARGS__ macro
- _VC_NODEFAULTLIB macro
- _WCHAR_T_DEFINED macro
- _WIN32 macro
- _WIN64 macro
- _WINRT_DLL macro
- __func__ identifier
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
ms.openlocfilehash: dedcab9b0addd3696749b50fef92b70081981c03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179905"
---
# <a name="predefined-macros"></a>Vordefinierte Makros

Der Microsoft C/C++-Compiler (MSVC) sind bestimmte Präprozessormakros, abhängig von der Sprache (C oder C++), kompilierungszielparameter und die ausgewählten Compileroptionen vordefiniert.

MSVC unterstützt die vordefinierten Präprozessormakros ANSI/ISO C99-Standard und der ISO C ++ 14 und C ++ 17-Standard erforderlich ist. Die Implementierung unterstützt auch verschiedene weitere Microsoft-spezifischen Präprozessormakros. Einige Makros sind nur für bestimmte Buildumgebungen oder Optionen für den Compiler definiert. Mit der Ausnahme nicht anders angegeben, die Makros, die während einer Übersetzungseinheit definiert sind, als ob sie als angegeben wurden **/d** compilerargumente-Option. Wenn definiert, werden die Makros vom Präprozessor vor der Kompilierung auf die angegebenen Werte erweitert. Die vordefinierten Makros, die keine Argumente annehmen und können nicht neu definiert werden.

## <a name="standard-predefined-identifier"></a>Vordefinierte Standardbezeichner

Der Compiler unterstützt diese vordefinierten Bezeichner gemäß ISO C99- und ISO C ++ 11.

- **&#95;&#95;Func&#95; &#95;**  den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion als eine lokale Funktion **static Const** Array von **Char**.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standard vordefinierte Makros

Der Compiler unterstützt diesen vordefinierten Makros, die durch die ISO C99- und ISO C ++ 17-Standard angegeben.

- **&#95;&#95;Cplusplus** als ein Integer-Literalwert definiert werden, wenn der Übersetzungseinheit als C++ kompiliert wird. Anderenfalls ist nicht definiert.

- **&#95;&#95;Datum&#95; &#95;**  das kompilierungsdatum der aktuellen Quelldatei. Das Datum ist eine Konstante Länge Zeichenfolgenliteral des Formats *Mmm TT JJJJ*. Der Name des Monats *Mmm* ist identisch mit den abgekürzten Monatsnamen generiert, indem Sie die C-Laufzeitbibliothek (CRT) [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Das erste Zeichen des Datums *TT* ein Leerzeichen ist, wenn der Wert kleiner als 10 ist. Dieses Makro wird immer definiert.

- **&#95;&#95;Datei&#95; &#95;**  den Namen der aktuellen Quelldatei. **&#95;&#95;Datei&#95; &#95;**  wird auf ein Zeichenfolgenliteral erweitert. Um sicherzustellen, dass der vollständige Pfad zur Datei angezeigt wird, verwenden [/FC (vollständiger Pfad der Quellcodedatei in Diagnose)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Dieses Makro wird immer definiert.

- **&#95;&#95;Zeile&#95; &#95;**  als die ganze Zahl Zeilennummer in der aktuellen Quelldatei definiert. Der Wert des der **&#95; &#95;Zeile&#95; &#95;** Makro kann geändert werden, indem eine `#line` Richtlinie. Dieses Makro wird immer definiert.

- **&#95;&#95;STDC&#95; &#95;**  als 1 definiert wird, nur, wenn als C kompiliert und die [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption angegeben ist. Anderenfalls ist nicht definiert.

- **&#95;&#95;STDC&#95;GEHOSTETER&#95; &#95;**  als 1 definiert wird, wenn die Implementierung ist eine *gehostete Implementierung*, eine Version, die gesamte erforderliche standard-Bibliothek unterstützt. Andernfalls definiert als 0.

- **&#95;&#95;STDCPP&#95;THREADS&#95; &#95;**  nur, wenn ein Programm mehr als einem Thread der Ausführung verfügen, kann auf 1 festgelegt, und als C++ kompiliert wird. Anderenfalls ist nicht definiert.

- **&#95;&#95;Zeit&#95; &#95;**  die Uhrzeit der Übersetzung der vorverarbeiteten Übersetzungseinheit. Die Zeit ist eine Zeichenfolge Zeichenfolgenliteral des Formats *hh: mm:*, die identisch mit der Zeit, die von der CRT zurückgegebenen [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Dieses Makro wird immer definiert.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft-spezifische vordefinierte Makros

MSVC unterstützt diese zusätzlichen vordefinierte Makros.

- **&#95;&#95;ATOM&#95; &#95;**  definiert als 1, wenn die [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) Compileroption festgelegt ist, und ist das compilerziel X86 oder X64. Anderenfalls ist nicht definiert.

- **&#95;&#95;AVX&#95; &#95;**  definiert als 1, wenn die [/arch: AVX](../build/reference/arch-x86.md) oder [/arch: avx2](../build/reference/arch-x86.md) Compileroptionen festgelegt und das compilerziel X86 oder X64. Anderenfalls ist nicht definiert.

- **&#95;&#95;AVX2&#95; &#95;**  definiert als 1, wenn die [/arch: avx2](../build/reference/arch-x86.md) Compileroption festgelegt ist, und ist das compilerziel X86 oder X64. Anderenfalls ist nicht definiert.

- **&#95;CHAR&#95;"UNSIGNED"** definiert als 1, wenn der Standardwert **Char** Typ ohne Vorzeichen ist. Dieser Wert wird definiert beim der [/j (standardmäßig "der Typ ist unsigned Char")](../build/reference/j-default-char-type-is-unsigned.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;&#95;CLR&#95;VER** definiert, wie ein Integer-Literal, das die Version der Common Language Runtime (CLR) darstellt, die zum Kompilieren der app verwendet. Der Wert ist in der Form codiert `Mmmbbbbb`, wobei `M` ist die Hauptversion der Runtime, `mm` die Nebenversion der Laufzeit und `bbbbb` ist die Nummer des Builds. **&#95;&#95;CLR&#95;VER** wird definiert, wenn die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;Steuerelement&#95;FLOW&#95;schützen** definiert als 1, wenn die [/Guard: CF (Ablaufsteuerungsschutz aktivieren)](../build/reference/guard-enable-control-flow-guard.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;&#95;LEISTUNGSINDIKATOR&#95; &#95;**  wird erweitert, um ein Integer-literal, das bei 0 beginnt. Der Wert wird um 1 erhöht, jedes Mal, wenn es in einer Quelldatei verwendet oder enthalten in den Headern der Quelldatei. **&#95;&#95;LEISTUNGSINDIKATOR&#95; &#95;**  speichert den Zustand beim Verwenden vorkompilierter Header. Dieses Makro wird immer definiert.

  Dieses Beispiel verwendet `__COUNTER__` um eindeutige Bezeichner drei verschiedenen Objekten desselben Typs zuzuweisen. Die `exampleClass` Konstruktor nimmt eine ganze Zahl als Parameter. In `main`, die Anwendung deklariert drei Objekte des Typs `exampleClass`mit `__COUNTER__` als eindeutiger bezeichnerparameter:

    ```cpp
    // macro__COUNTER__.cpp
    // Demonstration of __COUNTER__, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp
    #include <stdio.h>

    class exampleClass {
        int m_nID;
    public:
        // initialize object with a read-only unique ID
        exampleClass(int nID) : m_nID(nID) {}
        int GetID(void) { return m_nID; }
    };

    int main()
    {
        // __COUNTER__ is initially defined as 0
        exampleClass e1(__COUNTER__);

        // On the second reference, __COUNTER__ is now defined as 1
        exampleClass e2(__COUNTER__);

        // __COUNTER__ is now defined as 2
        exampleClass e3(__COUNTER__);

        printf("e1 ID: %i\n", e1.GetID());
        printf("e2 ID: %i\n", e2.GetID());
        printf("e3 ID: %i\n", e3.GetID());

        // Output
        // ------------------------------
        // e1 ID: 0
        // e2 ID: 1
        // e3 ID: 2

        return 0;
    }
    ```

- **&#95;&#95;Cplusplus&#95;Cli** als den Integer-Literalwert 200406 beim Kompilieren als C++ definiert und eine ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert. Wenn definiert,  **&#95; &#95;Cplusplus&#95;Cli** ist während der Übersetzungseinheit wirksam.

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef __cplusplus_cli
          printf("%d\n", __cplusplus_cli);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- **&#95;&#95;Cplusplus&#95;Winrt** als den Integer-Literalwert 201009 beim Kompilieren als C++ definiert und die [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;CPPRTTI** definiert als 1, wenn die [/GR (Laufzeit-Typinformationen aktivieren)](../build/reference/gr-enable-run-time-type-information.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;CPPUNWIND** als 1 definiert wird, wenn mindestens eines der [/GX (Ausnahmebehandlung aktivieren)](../build/reference/gx-enable-exception-handling.md), [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md), oder  [ /EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md) Compileroptionen festgelegt sind. Anderenfalls ist nicht definiert.

- **&#95;DEBUGGEN von** definiert als 1, wenn die ["/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), oder [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;DLL** definiert als 1, wenn die [/MD](../build/reference/md-mt-ld-use-run-time-library.md) oder [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) -Compileroption (Multithreaded DLL) festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;&#95;FUNCDNAME&#95; &#95;**  definiert als literal eine Zeichenfolge, enthält die [ergänzten Namen](../build/reference/decorated-names.md) der einschließenden Funktion. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95;FUNCDNAME&#95; &#95;** Makros nicht erweitert werden, bei der Verwendung der [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption.

   Dieses Beispiel verwendet die `__FUNCDNAME__`, `__FUNCSIG__`, und `__FUNCTION__` Makros um Funktionsinformationen anzuzeigen.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95;FUNCSIG&#95; &#95;**  definiert als ein Zeichenfolgenliteral, das die Signatur der einschließenden Funktion enthält. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95;FUNCSIG&#95; &#95;** Makros nicht erweitert werden, bei der Verwendung der [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Wenn für ein 64-Bit-Ziel kompiliert wird, ist die Aufrufkonvention `__cdecl` standardmäßig. Ein Beispiel der Nutzung finden Sie unter den `__FUNCDNAME__` Makro.

- **&#95;&#95;Funktion&#95; &#95;**  definiert als ein Zeichenfolgenliteral, das den nicht ergänzten Namen der einschließenden Funktion enthält. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95;Funktion&#95; &#95;** Makros nicht erweitert werden, bei der Verwendung der [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Ein Beispiel der Nutzung finden Sie unter den `__FUNCDNAME__` Makro.

- **&#95;GANZZAHLIGE&#95;MAX&#95;BITS** definiert als literal Ganzzahlwert 64, die maximale Größe (in Bit) für einen ganzzahligen Typ mit nicht-Vektor. Dieses Makro wird immer definiert.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95;&#95;INTELLISENSE&#95; &#95;**  definiert, wie 1, während ein IntelliSense-Compilers in Visual Studio-IDE übergeben. Anderenfalls ist nicht definiert. Sie können dieses Makro verwenden, um Code zu schützen, die IntelliSense-Compilers nicht verstehen, oder verwenden, um zwischen den Build und IntelliSense-Compilers zu wechseln. Weitere Informationen finden Sie unter [Tipps zur Problembehandlung für IntelliSense Langsamkeit](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/).

- **&#95;ISO&#95;flüchtige** definiert als 1, wenn die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;KERNEL&#95;Modus** definiert als 1, wenn die [/Kernel (Create-Kernel-Modus Binary)](../build/reference/kernel-create-kernel-mode-binary.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;AMD64** definiert, wie das Ganzzahlliteral Wert 100 für Kompilierungen, X64-Prozessoren. Anderenfalls ist nicht definiert.

- **&#95;M&#95;ARM** definiert als literal Ganzzahlwert 7 für Kompilierungen, die auf ARM-Prozessoren abzielen. Anderenfalls ist nicht definiert.

- **&#95;M&#95;ARM&#95;ARMV7VE** definiert als 1, wenn die [/arch: armv7ve](../build/reference/arch-arm.md) Compileroption wird festgelegt, für Kompilierungen, die auf ARM-Prozessoren abzielen. Anderenfalls ist nicht definiert.

- **&#95;M&#95;ARM&#95;FP** definiert als literal ganze Zahl, die angibt, [/arch](../build/reference/arch-arm.md) Compileroption für ARM-Prozessor Ziele festgelegt wurde. Anderenfalls ist nicht definiert.

  - Ein Wert im Bereich von 30-39 ohne Festlegung `/arch` ARM-Option wird angegeben, dass die standardmäßige Architektur für ARM wurde festgelegt (`VFPv3`).

  - Ein Wert im Bereich 40-49, wenn `/arch:VFPv4` festgelegt wurde.

  - Weitere Informationen finden Sie unter [/arch (ARM)](../build/reference/arch-arm.md).

- **&#95;M&#95;ARM64** definiert, wie 1 für Kompilierungen, die auf 64-Bit-ARM-Prozessoren abzielen. Anderenfalls ist nicht definiert.

- **&#95;M&#95;CEE** als definiert, 001 Wenn alle [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;CEE&#95;REINER** ab Visual Studio 2015 veraltet. Als definiert, 001, wenn die [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;CEE&#95;sicher** ab Visual Studio 2015 veraltet. Als definiert, 001, wenn die [/CLR: safe](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;FP&#95;EXCEPT** definiert als 1, wenn die [/fp: mit Ausnahme von](../build/reference/fp-specify-floating-point-behavior.md) oder [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;FP&#95;schnell** definiert als 1, wenn die [fast](../build/reference/fp-specify-floating-point-behavior.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;FP&#95;PRECISE** definiert als 1, wenn die [/fp: präzise](../build/reference/fp-specify-floating-point-behavior.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;FP&#95;STRICT** definiert als 1, wenn die [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;M&#95;IX86** definiert, wie das Ganzzahlliteral Wert von 600 für Kompilierungen, X86-Prozessoren. Dieses Makro ist nicht für X64 oder ARM-kompilierungsziele definiert.

- **&#95;M&#95;IX86&#95;FP** definiert als literal ganzzahligen Wert, der angibt der [/arch](../build/reference/arch-arm.md) -Compileroption, die Gruppe oder die Standardeinstellung wurde. Dieses Makro wird immer definiert werden, wenn das Kompilierungsziel x X86 ist Prozessor. Anderenfalls ist nicht definiert. Wenn definiert, ist der Wert auf:

  - 0, wenn die `/arch:IA32` Compileroption wurde festgelegt.

  - 1, wenn die `/arch:SSE` Compileroption wurde festgelegt.

  - 2, wenn die `/arch:SSE2`, `/arch:AVX`, oder `/arch:AVX2` Compileroption wurde festgelegt. Dieser Wert ist die Standardeinstellung, wenn ein `/arch` -Compileroption wurde nicht angegeben. Wenn `/arch:AVX` angegeben wird, das Makro **&#95; &#95;AVX&#95; &#95;** definiert. Wenn `/arch:AVX2` angegeben ist, beide **&#95; &#95;AVX&#95; &#95;** und **&#95; &#95;AVX2&#95; &#95;** ebenfalls definiert werden.

  - Weitere Informationen finden Sie unter [/arch (x86)](../build/reference/arch-x86.md).

- **&#95;M&#95;X64** definiert, wie das Ganzzahlliteral Wert 100 für Kompilierungen, X64-Prozessoren. Anderenfalls ist nicht definiert.

- **&#95;VERWALTETE** definiert als 1, wenn die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;MSC&#95;erstellen** definiert als ein Ganzzahlliteral, das die Revision Number-Element der Versionsnummer des Compilers enthält. Die Revisionsnummer ist das vierte Element der durch Punkte getrennten Versionsnummer. Die Versionsnummer des Microsoft C/C++-Compilers beispielsweise "15.00.20706.01" ist, die  **&#95;MSC&#95;erstellen** -Makro in 1 ausgewertet. Dieses Makro wird immer definiert.

- **&#95;MSC&#95;ERWEITERUNGEN** definiert als 1, wenn die auf standardmäßigen [/Ze (Spracherweiterungen aktivieren)](../build/reference/za-ze-disable-language-extensions.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;MSC&#95;vollständige&#95;VER** definiert als ein Integer-literal, die die wichtigsten codiert, neben- und erstellen Sie die Anzahl der Elemente der Versionsnummer des Compilers. Die Nummer die Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer, die kleinere Zahl ist das zweite Element und die Buildnummer ist das dritte Element. Die Versionsnummer des Microsoft C/C++-Compilers beispielsweise "15.00.20706.01" ist, die  **&#95;MSC&#95;vollständige&#95;VER** -Makro in 150020706 ausgewertet ausgewertet. Geben Sie `cl /?` in der Befehlszeile zum Anzeigen der Versionsnummer des Compilers. Dieses Makro wird immer definiert.

- **&#95;MSC&#95;VER** definiert als ein Ganzzahlliteral, das die Haupt- und Anzahl der Elemente der Versionsnummer des Compilers codiert. Die Nummer die Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer und die Nummer die Nebenversion ist das zweite Element. Wenn die Versionsnummer der Microsoft C/C++-Compiler "17.00.51106.1" ist, wird z. B. die  **&#95;MSC&#95;VER** -Makro in 1700 ausgewertet. Geben Sie `cl /?` in der Befehlszeile zum Anzeigen der Versionsnummer des Compilers. Dieses Makro wird immer definiert.

   |Visual Studio-Version|**&#95;MSC&#95;VER**|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 (7.0)|1300|
   |Visual Studio .NET 2003 (7.1)|1310|
   |Visual Studio 2005 (8.0)|1400|
   |Visual Studio 2008 (9.0)|1500|
   |Visual Studio 2010 (10.0)|1600|
   |Visual Studio 2012 (11.0)|1700|
   |Visual Studio 2013 (12.0)|1800|
   |Visual Studio 2015 (14.0)|1900|
   |Visual Studio 2017 RTW (15.0)|1910|
   |Visual Studio 2017 Version 15.3|1911|
   |Visual Studio 2017 Version 15.5|1912|
   |Visual Studio 2017 Version 15.6|1913|
   |Visual Studio 2017-Version 15.7|1914|
   |Visual Studio 2017 Version 15.8|1915|
   |Visual Studio 2017, Version 15.9|1916|
   |Visual Studio 2019 RTW (16,0)|1920|

   So testen Sie für die Compiler-Versionen oder Updates in einer bestimmten Version von Visual Studio oder nach dem, verwenden die **>=** Operator. Können Sie sie in einer bedingten Anweisung zum Vergleichen  **&#95;MSC&#95;VER** für diese bekannten Version. Wenn Sie mehrere sich gegenseitig ausschließende Versionen zu vergleichende verfügen, Sortieren Sie die Vergleiche in absteigender Reihenfolge der Versionsnummer. Dieser Code sucht z. B. Compiler veröffentlicht in Visual Studio 2017 und höher. Als Nächstes überprüft für veröffentlicht in oder nach Visual Studio 2015-Compiler. Anschließend überprüft er alle Compiler vor Visual Studio 2015 veröffentlicht:

   ```cpp
   #if _MSC_VER >= 1910
   // . . .
   #elif _MSC_VER >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   Weitere Informationen finden Sie unter [Visual C++-Compilerversion](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/) im Microsoft C++-Teamblog.

- **&#95;MSVC&#95;LANG** definiert als ein Integer-literal, der angibt, die für die der Compiler C++-Sprachstandard. Es wird nur im als C++ kompilierten Code festgelegt. Das Makro ist das Ganzzahlliteral Wert 201402L standardmäßig oder wenn die [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben ist. Das Makro auf 201703L festgelegt ist, wenn die [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben ist. Es wird festgelegt, auf einen Wert höher, nicht angegeben beim der [/Std: c ++ neueste](../build/reference/std-specify-language-standard-version.md) angegeben wird. Das Makro ist, andernfalls nicht definiert. Die  **&#95;MSVC&#95;LANG** Makro und [/Std (Specify Language Standard Version)](../build/reference/std-specify-language-standard-version.md) Compileroptionen sind ab Visual Studio 2015 Update 3.

- **&#95;&#95;MSVC&#95;RUNTIME&#95;überprüft** definiert als 1, wenn eine von der [/RTC](../build/reference/rtc-run-time-error-checks.md) Compileroptionen festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;MT** als 1, wenn definiert [/MD oder/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded DLL) oder [/MT oder/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded) angegeben wurde. Anderenfalls ist nicht definiert.

- **&#95;NATIVE&#95;WCHAR&#95;T&#95;definierte** definiert als 1, wenn die [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;OPENMP** als Integer-literal 200203, definiert werden, wenn die [/OpenMP (Aktivieren der OpenMP 2.0-Unterstützung)](../build/reference/openmp-enable-openmp-2-0-support.md) Compiler-Option festgelegt ist. Dieser Wert stellt dar, das Datum der OpenMP-Spezifikation von MSVC implementiert wird. Anderenfalls ist nicht definiert.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;**  definiert als 1, wenn die [/ analyze](../build/reference/analyze-code-analysis.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;&#95;Zeitstempel&#95; &#95;**  definiert als ein Zeichenfolgenliteral, das Datum und Uhrzeit der letzten Änderung der aktuellen Quelldatei, in Form von CRT zurückgegeben abgekürzten, Konstante Länge enthält [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion, z. B. `Fri 19 Aug 13:32:58 2016`. Dieses Makro wird immer definiert.

- **&#95;VC&#95;NODEFAULTLIB** definiert als 1, wenn die [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md) Compiler-Option festgelegt ist. Anderenfalls ist nicht definiert.

- **&#95;WCHAR&#95;T&#95;definierte** definiert als 1, wenn der Standardwert [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Compiler-Option festgelegt ist. Die  **&#95;WCHAR&#95;T&#95;definierte** -Makro wird definiert, aber keinen Wert besitzt, wenn die `/Zc:wchar_t-` Compileroption festgelegt ist, und **"wchar_t"** wird in einer systemheaderdatei in enthaltenen definiert Ihre Projekt. Anderenfalls ist nicht definiert.

- **&#95;Win32** definierte als 1, wenn das Kompilierungsziel 32-Bit-ARM, 64-Bit-ARM X86, ist "oder" x 64. Anderenfalls ist nicht definiert.

- **&#95;Win64** Wenn kompilierungszielparameter 64-Bit-ARM oder X64 ist auf 1 festgelegt. Anderenfalls ist nicht definiert.

- **&#95;WINRT&#95;DLL** definiert als 1, wenn als C++ und die beiden kompiliert [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) und [/ld oder "/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md) Compileroptionen festgelegt sind. Anderenfalls ist nicht definiert.

Keine Präprozessormakros, die identifizieren, die ATL oder MFC-Bibliotheksversion werden vom Compiler vordefinierte. Definieren diese Makros Version intern, ATL und MFC-Bibliothek-Header. Sie sind nicht definiert, in präprozessoranweisungen vorgenommen werden, bevor Sie der erforderliche Header enthalten ist.

- **&#95;ATL&#95;VER** in definierten \<atldef.h > als ein Integer-literal, die die Versionsnummer des ATL-codiert.

- **&#95;MFC&#95;VER** in definierten \<afxver_.h > als ein Ganzzahlliteral, das die MFC-Versionsnummer codiert.

## <a name="see-also"></a>Siehe auch

[Makros (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)<br/>
[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)