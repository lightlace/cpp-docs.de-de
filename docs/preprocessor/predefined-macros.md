---
title: Vordefinierte Makros | Microsoft Docs
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53acac18902e261eede565987d6b9c053a8f1707
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="predefined-macros"></a>Vordefinierte Makros

Visual C++-Compilers sind bestimmte Präprozessormakros, abhängig von der Sprache (C oder C++), das Kompilierungsziel und die ausgewählten Compileroptionen vordefiniert.

Visual C++ unterstützt die erforderliche vordefinierten Präprozessormakros gemäß dem Standard ANSI/ISO C99 und ISO C ++ 14-standard. Die Implementierung unterstützt auch mehrere weitere Microsoft-spezifische Präprozessormakros. Einige Makros sind nur für bestimmte Buildumgebungen oder Compileroptionen definiert. Sofern nicht angegeben, werden die Makros in der gesamten Übersetzungseinheit definiert, als ob sie als angegeben wurden **/d** Optionsargumente Compiler. Wenn definiert, werden die Makros vom Präprozessor vor der Kompilierung auf die angegebenen Werte erweitert. Die vordefinierten Makros akzeptieren keine Argumente und können nicht neu definiert werden.

## <a name="standard-predefined-identifier"></a>Vordefinierte Standardbezeichner

Der Compiler unterstützt diese vordefinierten Bezeichner, die durch ISO C99 und ISO C ++ 11 angegeben.

- **&#95; &#95; Func &#95; &#95;**  Den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion als eine Funktion lokale `static const` Array von `char`.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standard vordefinierte Makros

Der Compiler unterstützt diesen vordefinierten Makros, die durch die ISO C99 und ISO C ++ 17-Standard angegeben.

- **&#95; &#95; Cplusplus** als ein Integer-Literalwert definiert werden, wenn der Übersetzungseinheit als C++ kompiliert wird. Andernfalls nicht definiert.

- **&#95; &#95; Datum &#95; &#95;**  Das kompilierungsdatum der aktuellen Quelldatei. Das Datum ist eine Zeichenfolge der Länge der Konstante Zeichenfolgenliteral des Formats *Mmm Dd Yyyy*. Der Name des Monats *Mmm* ist identisch mit den abgekürzten Monatsnamen in Datumsangaben, die von der C-Laufzeitbibliothek generiert [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Das erste Zeichen des Datums *Dd* ein Leerzeichen ist, wenn der Wert kleiner als 10 ist. Dieses Makro wird immer definiert.

- **&#95; &#95; Datei &#95; &#95;**  Den Namen der aktuellen Quelldatei. **&#95; &#95; Datei &#95; &#95;**  wird auf ein Zeichenfolgenliteral erweitert. Um sicherzustellen, dass der vollständige Pfad zur Datei angezeigt wird, verwenden [/FC (vollständiger Pfad der Quellcodedatei in Diagnostics)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Dieses Makro wird immer definiert.

- **&#95; &#95; LINE #95; &#95;**  Definiert als die ganze Zahl Zeilennummer in der aktuellen Quelldatei. Der Wert, der die **&#95; &#95; LINE #95; &#95;**  Makro kann geändert werden, indem eine `#line` Richtlinie. Dieses Makro wird immer definiert.

- **&#95; &#95; STDC++ &#95; &#95;**  Als 1 definiert wird, nur, wenn als C kompiliert und die ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption angegeben ist. Andernfalls nicht definiert.

- **&#95;&#95;STDC&#95;HOSTED&#95;&#95;** Defined as 1 if the implementation is a *hosted implementation*, one that supports the entire required standard library. Definiert, andernfalls 0.

- **&#95; &#95; STDCPP &#95; THREADS &#95; &#95;**  Als 1 definiert wird, wenn ein Programm mehrere Ausführungsthreads haben kann und als C++ kompiliert wird. Andernfalls nicht definiert.

- **&#95; &#95; Zeit &#95; &#95;**  Die Uhrzeit der Übersetzung der vorverarbeiteten Übersetzungseinheit. Die Zeit ist eine Zeichenfolge Zeichenfolgenliteral des Formats *hh: mm:*, identisch mit der Zeit von der C-Laufzeitbibliothek zurückgegeben [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Dieses Makro wird immer definiert.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft-spezifische vordefinierte Makros

Microsoft Visual C++ unterstützt diesen zusätzlichen vordefinierten Makros.

- **&#95; &#95; ATOM &#95; &#95;**  Als When 1 definiert die [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) (Compileroption) festgelegt ist und das Ziel der Compiler X86 oder X64. Andernfalls nicht definiert.

- **&#95; &#95; AVX &#95; &#95;**  Als When 1 definiert die [/arch: AVX](../build/reference/arch-x86.md) oder [/arch: avx2](../build/reference/arch-x86.md) Compileroptionen werden festgelegt, und das Ziel der Compiler ist X86 oder X64. Andernfalls nicht definiert.

- **&#95; &#95; AVX2 &#95; &#95;**  Als When 1 definiert die [/arch: avx2](../build/reference/arch-x86.md) (Compileroption) festgelegt ist und das Ziel der Compiler X86 oder X64. Andernfalls nicht definiert.

- **&#95; CHAR &#95; Ohne Vorzeichen** definiert als 1, wenn die Standardeinstellung `char` Typ ohne Vorzeichen ist. Dadurch wird festgelegt, wenn die [/j (standardmäßig Typ unsigned Char)](../build/reference/j-default-char-type-is-unsigned.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; &#95; CLR &#95; VER** definiert als ein Ganzzahlliteral, das die Version der common Language Runtime verwendet, wenn es sich bei der Kompilierung der Anwendung darstellt. Der Wert ist in der Form codiert `Mmmbbbbb`, wobei `M` ist die Hauptversion der Laufzeit `mm` ist die Nebenversion der Laufzeit und `bbbbb` Nummer des Builds. **&#95; &#95; CLR &#95; VER** wird definiert, wenn die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95; Steuerelement &#95; FLUSS &#95; Schützen Sie** als When 1 definiert die [/Guard: CF (Ablaufsteuerungsschutz aktivieren)](../build/reference/guard-enable-control-flow-guard.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; &#95; LEISTUNGSINDIKATOR &#95; &#95;**  Wird erweitert, um ein Ganzzahlliteral, das beginnt bei 0 und wird um 1 erhöht, jedes Mal, wenn er in einer Quelldatei verwendet wird oder eingeschlossenen Headern der Quelldatei. **&#95; &#95; LEISTUNGSINDIKATOR &#95; &#95;**  speichert den Zustand beim Verwenden vorkompilierter Header. Dieses Makro wird immer definiert.

  Dieses Beispiel verwendet `__COUNTER__` eindeutige Bezeichner drei verschiedenen Objekten desselben Typs zugewiesen. Die `exampleClass` Konstruktor akzeptiert eine ganze Zahl als Parameter. In `main`, die Anwendung deklariert drei Objekte des Typs `exampleClass`mit `__COUNTER__` als eindeutiger bezeichnerparameter:

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

- **&#95; &#95; Cplusplus &#95;Cli** als Integer-Literalwert 200406 beim Kompilieren als C++ definiert und eine ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert. Wenn definiert, **&#95; &#95; Cplusplus &#95;Cli** während der Übersetzungseinheit wirksam wird.

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

- **&#95; &#95; Cplusplus &#95;Winrt** als Integer-Literalwert 201009 beim Kompilieren als C++ definiert und die [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; CPPRTTI** definiert als 1, wenn die [/GR (Laufzeit-Typinformationen aktivieren)](../build/reference/gr-enable-run-time-type-information.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; CPPUNWIND** als 1 definiert wird, wenn eine oder mehrere der der [/GX (Ausnahmebehandlung aktivieren)](../build/reference/gx-enable-exception-handling.md), [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md), oder  [ /EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md) Compileroptionen werden festgelegt. Andernfalls nicht definiert.

- **&#95; DEBUG** als When 1 definiert die ["/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), oder [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; DLL** als When 1 definiert die [/MD](../build/reference/md-mt-ld-use-run-time-library.md) oder [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) Compileroption (Multithreaded DLL) festgelegt ist. Andernfalls nicht definiert.

- **&#95; &#95; FUNCDNAME &#95; &#95;**  Definiert als eine literale Zeichenfolge, enthält die [ergänzten Namens in](../build/reference/decorated-names.md) der einschließenden Funktion. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95; FUNCDNAME &#95; &#95;**  Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption.

   Dieses Beispiel verwendet die `__FUNCDNAME__`, `__FUNCSIG__`, und `__FUNCTION__` Makros um Funktionsinformationen anzuzeigen.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95; &#95; FUNCSIG &#95; &#95;**  Definiert als ein Zeichenfolgenliteral, das die Signatur der einschließenden Funktion enthält. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95; FUNCSIG &#95; &#95;**  Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Wenn für eine 64-Bit-Ziele kompiliert wird, ist die Aufrufkonvention `__cdecl` standardmäßig. Ein Beispiel der Verwendung finden Sie unter der `__FUNCDNAME__` Makro.

- **&#95; &#95; FUNCTION &#95; &#95;**  Definiert als ein Zeichenfolgenliteral, das den nicht ergänzten Namen der einschließenden Funktion enthält. Das Makro ist nur innerhalb einer Funktion definiert. Die **&#95; &#95; FUNCTION &#95; &#95;**  Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Ein Beispiel der Verwendung finden Sie unter der `__FUNCDNAME__` Makro.

- **&#95; INTEGRALE &#95; Maximale &#95; BITS** definiert als die Integer-Literalwert 64, die maximale Größe (in Bits) für einen ganzzahligen Typ von nicht-Vektor. Dieses Makro wird immer definiert.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95; &#95; INTELLISENSE &#95; &#95;**  Definiert, wie 1, während ein IntelliSense-Compiler in Visual Studio-IDE übergeben. Andernfalls nicht definiert. Sie können dieses Makro verwenden, um Code zu schützen, die IntelliSense-Compiler nicht verstehen, oder verwenden, um zwischen den Build und IntelliSense-Compiler zu wechseln. Weitere Informationen finden Sie unter [Tipps zur Problembehandlung für IntelliSense dies darauf](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/).

- **&#95; ISO &#95; FLÜCHTIGE** definiert als 1, wenn die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; KERNEL &#95; Modus** definiert als 1, wenn die [/Kernel für den (erstellen Kernel-Modus binär)](../build/reference/kernel-create-kernel-mode-binary.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; AMD64** als Integer-literal Wert 100 für Kompilierungen, X64-Prozessoren definiert. Andernfalls nicht definiert.

- **&#95; Übe &#95; ARM** definiert als die Integer-Literalwert 7 für Kompilierungen, die auf ARM-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95; Übe &#95; ARM &#95; ARMV7VE** als When 1 definiert die [/arch: armv7ve](../build/reference/arch-arm.md) Compileroption für Kompilierungen, die auf ARM-Prozessoren abzielen festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; ARM &#95; FP** definiert als ein Integer-literal-Wert, der gibt an [/arch](../build/reference/arch-arm.md) Compileroption festgelegt wurde, ist das Kompilierungsziel eine ARM-Prozessor. Andernfalls nicht definiert.

  - Im Bereich 30-39 ohne Festlegung **/arch** ARM-Option wird angegeben, dass die standardmäßige Architektur für ARM festgelegt wurde (`VFPv3`).

  - Im Bereich 40-49, wenn **/arch: vfpv4** festgelegt wurde.

  - Finden Sie unter [/arch (ARM)](../build/reference/arch-arm.md) für Weitere Informationen.

- **&#95; Übe &#95; ARM64** definiert als 1 für Kompilierungen, die auf 64-Bit-ARM-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95; Übe &#95; CEE** als 001 If definiert eine [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; CEE &#95; REINE** ab Visual Studio 2015 veraltet. Als definiert, wenn 001 der [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; CEE &#95; Sichere** ab Visual Studio 2015 veraltet. Als definiert, wenn 001 der [/CLR: safe](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; FP &#95; Mit Ausnahme von** definiert als 1, wenn die [/fp: außer](../build/reference/fp-specify-floating-point-behavior.md) oder [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; FP &#95; Schnelle** definiert als 1, wenn die [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; FP &#95; PRÄZISE** definiert als 1, wenn die [/fp: präzise](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Übe &#95; FP &#95; STRICT** definiert als 1, wenn die [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; M &#95; IX86** als Integer-literal Wert von 600 für Kompilierungen, X86-Prozessoren definiert. Dieses Makro ist nicht für X64 oder ARM-kompilierungsziele definiert.

- **&#95; Übe &#95; IX86 &#95; FP** definiert als ein Integer-Literalwert, der angibt der [/arch](../build/reference/arch-arm.md) (Compileroption), die Gruppe oder die Standardeinstellung wurde. Dieses Makro wird immer definiert, wenn das Kompilierungsziel x X86 ist Prozessor. Andernfalls nicht definiert. Wenn definiert, ist der Wert auf:

  - 0, wenn die **/arch:IA32** Compileroption festgelegt wurde.

  - 1, wenn die **neben** Compileroption festgelegt wurde.

  - 2, wenn die **SSE2**, **/arch: AVX** oder **/arch: avx2** Compileroption festgelegt wurde. Dieser Wert ist die Standardeinstellung, wenn ein **/arch** Compileroption wurde nicht angegeben. Wenn **/arch: AVX** angegeben wird, das Makro **&#95; &#95; AVX &#95; &#95;**  auch definiert ist. Wenn **/arch: avx2** angegeben wird, sowohl **&#95; &#95; AVX &#95; &#95;**  und **&#95; &#95; AVX2 &#95; &#95;**  sind auch definiert.

  - Finden Sie unter [/arch (x86)](../build/reference/arch-x86.md) für Weitere Informationen.

- **&#95; Übe &#95; X64** als Integer-literal Wert 100 für Kompilierungen, X64-Prozessoren definiert. Andernfalls nicht definiert.

- **&#95; VERWALTET** als When 1 definiert die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; MSC &#95; Erstellen Sie** als ein Ganzzahlliteral, das die Anzahl Revision-Element der Versionsnummer des Compilers enthält definiert. Die Revisionsnummer ist das vierte Element der durch Punkte getrennten Versionsnummer. Die Versionsnummer des Visual C++-Compilers beispielsweise "15.00.20706.01" ist, die **&#95; MSC &#95; Erstellen Sie** -Makro in 1 ausgewertet. Dieses Makro wird immer definiert.

- **&#95; MSC &#95; ERWEITERUNGEN** definiert als 1, wenn die [/Ze (Spracherweiterungen aktivieren)](../build/reference/za-ze-disable-language-extensions.md) (Compileroption) festgelegt ist, dies ist die Standardeinstellung. Andernfalls nicht definiert.

- **&#95; MSC &#95; VOLLSTÄNDIGE &#95; VER** definiert als ein Ganzzahlliteral, das die Hauptversionsnummer codiert, kleinere und erstellen Sie die Anzahl der Elemente der Versionsnummer des Compilers. Die Nummer der Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer und die Buildnummer ist das dritte Element die Nebenversionsnummer ist das zweite Element. Die Versionsnummer des Visual C++-Compilers beispielsweise "15.00.20706.01" ist, die **&#95; MSC &#95; VOLLSTÄNDIGE &#95; VER** -Makro in 150020706 ausgewertet ausgewertet. Geben Sie **cl /?** in der Befehlszeile, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.

- **&#95; MSC &#95; VER** definiert als ein Ganzzahlliteral, das die Haupt- und Nebenversionsnummern Anzahl der Elemente der Versionsnummer des Compilers codiert. Die Nummer der Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer und die Nebenversionsnummer ist das zweite Element. Die Versionsnummer des Visual C++-Compilers beispielsweise "17.00.51106.1" ist, die **&#95; MSC &#95; VER** -Makro in 1700 ausgewertet. Geben Sie **cl /?** in der Befehlszeile, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.

- **&#95; MSVC &#95; LANG** definiert als ein Integer-literal, der angibt, die C++-sprachenstandard, durch den Compiler vorgesehen. Wenn als C++ kompiliert wird, ist das Makro die Integer-Literalwert 201402L, wenn die [/std:c ++ 14](../build/reference/std-specify-language-standard-version.md) (Compileroption) festgelegt ist, oder in der Standardeinstellung; wird festgelegt, um 201703 L Wenn die [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md) (Compileroption) festgelegt ist; und ist ein höhere, nicht angegebener Wert, wenn die [/std:c ++ neueste](../build/reference/std-specify-language-standard-version.md). Das Makro ist, andernfalls nicht definiert. Die **&#95; MSVC &#95; LANG** Makro und [/std (Geben Sie Standard Sprachversion)](../build/reference/std-specify-language-standard-version.md) Compileroptionen sind ab Visual Studio 2015 Update 3.

- **&#95; &#95; MSVC &#95; Common Language RUNTIME &#95; ÜBERPRÜFT** definiert als 1, wenn mindestens ein von der [/RTC](../build/reference/rtc-run-time-error-checks.md) Compileroptionen festgelegt ist. Andernfalls nicht definiert.

- **&#95; MT** als 1 When definiert [/MD oder/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded DLL) oder [/MT oder/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded) angegeben. Andernfalls nicht definiert.

- **&#95; SYSTEMEIGENE &#95; WCHAR &#95; T &#95; benutzerdefinierte** als When 1 definiert die [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; OPENMP** definiert, die als ganze Zahl literal 200203, das Datum der OpenMP-Spezifikation, die von Visual C++ implementierte darstellt, wenn die [/OpenMP (Aktivieren der OpenMP 2.0-Unterstützung)](../build/reference/openmp-enable-openmp-2-0-support.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95; PREFAST &#95;**  Als When 1 definiert die [/ analyze](../build/reference/analyze-code-analysis.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; &#95; TIMESTAMP &#95; &#95;**  Definiert als ein Zeichenfolgenliteral, das Datum und Uhrzeit der letzten Änderung der aktuellen Quelldatei, in Form abgekürzten, Konstante Länge zurückgegeben, die von der C-Laufzeitbibliothek enthält [Asctime](../c-runtime-library/reference/asctime-wasctime.md) funktionieren, z. B. `Fri 19 Aug 13:32:58 2016`. Dieses Makro wird immer definiert.

- **&#95; VC &#95; NODEFAULTLIB** als When 1 definiert die [Zl (lassen Sie die Namen der Bibliothek)](../build/reference/zl-omit-default-library-name.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.

- **&#95; WCHAR &#95; T &#95; benutzerdefinierte** als When 1 definiert die Standardeinstellung [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) (Compileroption) festgelegt ist. Die **&#95; WCHAR &#95; T &#95; benutzerdefinierte** -Makro wird definiert, aber kein Wert vorliegt, wenn die **/Zc:wchar_t-** (Compileroption) festgelegt ist, und `wchar_t` wird definiert, in einer systemheaderdatei im Projekt enthalten. Andernfalls nicht definiert.

- **&#95; Win32** definiert als 1, wenn die Kompilierungsziel mit 32-Bit-ARM "," 64-Bit-ARM "," X86, ist oder x 64. Andernfalls nicht definiert.

- **&#95; Win64** als 1 definiert wird, wenn das Kompilierungsziel 64-Bit-ARM oder X64 ist. Andernfalls nicht definiert.

- **&#95; WINRT &#95; DLL** definiert, wie C++ und sowohl als 1 When kompiliert [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) und [/ld oder "/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md) Compileroptionen werden festgelegt. Andernfalls nicht definiert.

 Bestimmt die ATL- oder MFC-Bibliotheksversion Präprozessormakros werden vom Compiler nicht vordefiniert. Diese Makros werden in den Headern für die Bibliothek definiert, damit sie in den Präprozessordirektiven nicht definiert werden, bevor die erforderlichen Header enthalten ist.

- **&#95; ATL- &#95; VER** in definierten \<atldef.h > als ein Ganzzahlliteral, das die ATL-Versionsnummer codiert.

- **&#95; MFC- &#95; VER** in definierten \<afxver_.h > als ein Ganzzahlliteral, das die MFC-Versionsnummer codiert.

## <a name="see-also"></a>Siehe auch

[Makros (C/C++)](../preprocessor/macros-c-cpp.md)   
[Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md)   
[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
