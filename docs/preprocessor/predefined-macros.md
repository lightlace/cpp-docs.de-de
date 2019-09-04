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
ms.openlocfilehash: 15b70b0292f671d99b320c8d23598e68b47adb0d
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273819"
---
# <a name="predefined-macros"></a>Vordefinierte Makros

Der Microsoft C/C++ Compiler (MSVC) definiert bestimmte Präprozessormakros in Abhängigkeit von der Sprache (c oder C++), dem Kompilierungs Ziel und den ausgewählten Compileroptionen.

MSVC unterstützt die vordefinierten Präprozessormakros, die vom ANSI/ISO C99-Standard und den ISO c++ 14-und c++ 17-Standards benötigt werden. Die Implementierung unterstützt auch mehrere weitere Microsoft-spezifische Präprozessormakros. Einige Makros werden nur für bestimmte Buildumgebungen oder Compileroptionen definiert. Sofern nicht angegeben, werden die Makros in einer Übersetzungseinheit definiert, als ob Sie als **/D** -compileroptionsargumente angegeben wurden. Wenn diese definiert ist, werden die Makros vor der Kompilierung durch den Präprozessor auf die angegebenen Werte erweitert. Die vordefinierten Makros akzeptieren keine Argumente und können nicht neu definiert werden.

## <a name="standard-predefined-identifier"></a>Vordefinierter Standard Bezeichner

Der Compiler unterstützt diesen vordefinierten Bezeichner, der von ISO C99 und ISO c++ 11 angegeben wird.

- **&#95;&#95; Func &#95;** Der nicht qualifizierte und ungeschützte Name der einschließenden Funktion als **statisches** konstantenarray von **char**.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standard mäßige vordefinierte Makros

Der Compiler unterstützt diese vordefinierten Makros, die von den ISO C99-und ISO c++ 17-Standards angegeben werden.

- **&#95; &#95;** Wird als ganzzahliger Literalwert definiert, wenn die Übersetzungs C++Einheit als kompiliert wird. Andernfalls nicht definiert.

- **&#95; Datum &#95; &#95;** Das Kompilierungs Datum der aktuellen Quelldatei. Das Datum ist ein Zeichenfolgenliteralzeichen mit konstanter Länge in der Form *mmm DD JJJJ*. Der Monats Name *mmm* entspricht dem abgekürzten Monatsnamen, der von der [Asctime](../c-runtime-library/reference/asctime-wasctime.md) -Funktion der C-Lauf Zeit Bibliothek (CRT) generiert wurde. Das erste Zeichen von Date *DD* ist ein Leerzeichen, wenn der Wert kleiner als 10 ist. Dieses Makro wird immer definiert.

- **&#95; Datei &#95; &#95;** Der Name der aktuellen Quelldatei. Die Datei wird zu einem Zeichenfolgenliteralzeichen **&#95; &#95;&#95;** Um sicherzustellen, dass der vollständige Pfad zur Datei angezeigt wird, verwenden Sie [/FC (vollständiger Pfad der Quell Code Datei in der Diagnose)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Dieses Makro wird immer definiert.

- **&#95; Zeile &#95; &#95;** Definiert als ganzzahlige Zeilennummer in der aktuellen Quelldatei. Der Wert des **&#95; &#95;Linien&#95;** Makros kann mit einer `#line` -Direktive geändert werden. Dieses Makro wird immer definiert.

- **&#95;&#95; Stdc &#95;** Wird nur dann als 1 definiert, wenn es als C kompiliert wird und die [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption angegeben wird. Andernfalls nicht definiert.

- **&#95;&#95;&#95;Gehostetes&#95; stdc** als 1 definiert, wenn es sich um eine *gehostete Implementierung*handelt, eine, die die gesamte erforderliche Standardbibliothek unterstützt. Andernfalls als 0 definiert.

- **&#95;&#95;Stdcpp&#95;-&#95; Threads** werden nur dann als 1 definiert, wenn ein Programm mehr als einen Ausführungs Thread aufweisen und als C++kompiliert werden kann. Andernfalls nicht definiert.

- **&#95; Uhrzeit &#95; &#95;** Der Zeitpunkt der Übersetzung der vorverarbeiteten Übersetzungseinheit. Die Zeit ist ein Zeichenfolgenliteral im Format *hh: mm: SS*, das der von der CRT [Asctime](../c-runtime-library/reference/asctime-wasctime.md) -Funktion zurückgegebenen Zeit entspricht. Dieses Makro wird immer definiert.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft-spezifische vordefinierte Makros

MSVC unterstützt diese zusätzlichen vordefinierten Makros.

- **&#95; Atom &#95; &#95;** Definiert als 1, wenn die [/favor: Atom](../build/reference/favor-optimize-for-architecture-specifics.md) -Compileroption festgelegt ist und das compilerziel x86 oder x64 ist. Andernfalls nicht definiert.

- **&#95;&#95; AVX &#95;** Definiert als 1, wenn die Compileroptionen [/arch: AVX](../build/reference/arch-x86.md) oder [/arch: AVX2](../build/reference/arch-x86.md) festgelegt sind und das compilerziel x86 oder x64 ist. Andernfalls nicht definiert.

- **&#95; AVX2 &#95; &#95;** Definiert als 1, wenn die [/arch: AVX2](../build/reference/arch-x86.md) -Compileroption festgelegt ist und das compilerziel x86 oder x64 ist. Andernfalls nicht definiert.

- **&#95;Char&#95;unsigned** ist als 1 definiert, wenn der standardmäßige **char** -Typ nicht signiert ist. Dieser Wert wird definiert, wenn die Compileroption [/J (Default char type is unsigned)](../build/reference/j-default-char-type-is-unsigned.md) festgelegt ist. Andernfalls nicht definiert.

- **CLR&#95;-ver &#95; &#95;** Definiert als Ganzzahlliteral, das die Version der Common Language Runtime (CLR) darstellt, die zum Kompilieren der APP verwendet wird. Der Wert `Mmmbbbbb`wird in der Form codiert, wobei `M` die Hauptversion der Laufzeit, `mm` die neben Version der Laufzeit und `bbbbb` die Buildnummer ist. **&#95;&#95;Der&#95;CLR-ver** ist definiert, wenn die [/CLR](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;Der&#95;Ablauf&#95;Steuerungs Wächter** ist als 1 definiert, wenn die Compileroption [/Guard: CF (Ablauf Steuerungs Schutz aktivieren)](../build/reference/guard-enable-control-flow-guard.md) festgelegt ist. Andernfalls nicht definiert.

- **&#95; Counter &#95; &#95;** Wird auf ein Ganzzahlliteral erweitert, das bei 0 beginnt. Der Wert wird jedes Mal um 1 erhöht, wenn er in einer Quelldatei oder in enthaltenen Headern der Quelldatei verwendet wird. Der-Wert speichert den Zustand, wenn Sie vorkompilierte Header verwenden. **&#95; &#95;&#95;** Dieses Makro wird immer definiert.

  In diesem Beispiel `__COUNTER__` wird verwendet, um drei verschiedenen Objekten desselben Typs eindeutige Bezeichner zuzuweisen. Der `exampleClass` Konstruktor nimmt eine ganze Zahl als Parameter an. In `main`deklariert die Anwendung drei Objekte des Typs `exampleClass`, wobei als `__COUNTER__` eindeutiger bezeichnerparameter verwendet wird:

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

- **&#95;&#95;CPlusPlus&#95;CLI** ist als ganzzahliger Literalwert 200406 definiert C++ , wenn kompiliert als und eine [/CLR](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption festgelegt wird. Andernfalls nicht definiert. Wenn die  **&#95; &#95;CPlusPlus&#95;-CLI** definiert ist, ist Sie in der gesamten Übersetzungseinheit wirksam.

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

- **&#95;&#95;CPlusPlus&#95;WinRT** wurde bei der Kompilierung als C++ der ganzzahlige Literalwert 201009 definiert, und die Compileroption [/ZW (Windows-Runtime Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) ist festgelegt. Andernfalls nicht definiert.

- **&#95;Cpprtti** Definiert als 1, wenn die [Compileroption/gr (Lauf Zeittyp Informationen aktivieren)](../build/reference/gr-enable-run-time-type-information.md) festgelegt ist. Andernfalls nicht definiert.

- **&#95;Cppentladen** Definiert als 1, wenn eine oder mehrere der [/GX (Ausnahmebehandlung aktivieren)](../build/reference/gx-enable-exception-handling.md), [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md)oder [/eh (Ausnahme Behandlungsmodell)](../build/reference/eh-exception-handling-model.md) -Compileroptionen festgelegt sind. Andernfalls nicht definiert.

- **&#95;Debuggen** Definiert als 1, wenn die [/ldd](../build/reference/md-mt-ld-use-run-time-library.md)-, [/MDD](../build/reference/md-mt-ld-use-run-time-library.md)-oder [/MTD](../build/reference/md-mt-ld-use-run-time-library.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- Die dll ist als 1 definiert, wenn die Compileroption [/MD](../build/reference/md-mt-ld-use-run-time-library.md) oder [/MDD](../build/reference/md-mt-ld-use-run-time-library.md) (Multithread-DLL) festgelegt ist.  **&#95;** Andernfalls nicht definiert.

- **&#95;Funcdname &#95;&#95;** Definiert als Zeichenfolgenliteralwert, der den ergänzten [Namen](../build/reference/decorated-names.md) der einschließenden Funktion enthält. Das-Makro wird nur innerhalb einer Funktion definiert. **&#95;Das &#95;funcdname&#95;** -Makro wird nicht erweitert, wenn Sie die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -oder [/P](../build/reference/p-preprocess-to-a-file.md) -Compileroption verwenden.

   In diesem Beispiel werden `__FUNCDNAME__`die `__FUNCSIG__`Makros, `__FUNCTION__` und verwendet, um Funktions Informationen anzuzeigen.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95; Funksig &#95;** Definiert als Zeichenfolgenliteralwert, der die Signatur der einschließenden Funktion enthält. Das-Makro wird nur innerhalb einer Funktion definiert. **&#95;Das &#95;funcsig&#95;** -Makro wird nicht erweitert, wenn Sie die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -oder [/P](../build/reference/p-preprocess-to-a-file.md) -Compileroption verwenden. Bei der Kompilierung für ein 64-Bit-Ziel ist `__cdecl` die Aufruf Konvention standardmäßig. Ein Beispiel für die Verwendung finden Sie im `__FUNCDNAME__` -Makro.

- **&#95;&#95; - &#95;Funktion** Definiert als Zeichenfolgenliterale, das den nicht ergänzten Namen der einschließenden Funktion enthält. Das-Makro wird nur innerhalb einer Funktion definiert. **&#95;Das &#95;Funktions&#95;** Makro wird nicht erweitert, wenn Sie die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -oder [/P](../build/reference/p-preprocess-to-a-file.md) -Compileroption verwenden. Ein Beispiel für die Verwendung finden Sie im `__FUNCDNAME__` -Makro.

- ganzzahlige **&#95;maximale&#95; &#95;** Definiert als ganzzahliger Literalwert 64, die maximale Größe (in Bit) für einen nicht Vektor-ganzzahligen Typ. Dieses Makro wird immer definiert.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95;&#95; IntelliSense &#95;** Definiert als 1 bei einem IntelliSense-compilerdurchlauf in der Visual Studio-IDE. Andernfalls nicht definiert. Sie können dieses Makro verwenden, um den Code zu schützen, den der IntelliSense-Compiler nicht versteht, oder Sie verwenden, um zwischen dem Build und dem IntelliSense-Compiler zu wechseln. Weitere Informationen finden Sie unter [Tipps zur Problembehandlung für IntelliSense-verlangsamtheit](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/).

- **&#95;ISO&#95;volatile** ist als 1 definiert, wenn die [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;Der&#95;** als 1 definierte Kernel Modus, wenn die Compileroption [/Kernel (Kernel Modus-Binärdatei erstellen)](../build/reference/kernel-create-kernel-mode-binary.md) festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;amd64** Definiert als ganzzahliger Literalwert 100 für Kompilierungen, die auf x64-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95;M&#95;Arm** Definiert als der ganzzahlige Literalwert 7 für Kompilierungen, die auf ARM-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95;M&#95;Arm&#95;ARMV7VE** definiert als 1, wenn die [/arch: ARMV7VE](../build/reference/arch-arm.md) -Compileroption für Kompilierungen festgelegt wird, die auf ARM-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95;M&#95;Arm&#95;FP** definiert als ganzzahliger Literalwert, der angibt, welche [/arch](../build/reference/arch-arm.md) -Compileroption für ARM-Prozessor Ziele festgelegt wurde. Andernfalls nicht definiert.

  - Ein Wert im Bereich 30-39, wenn keine `/arch` Arm-Option angegeben wurde, der angibt, dass die Standard Architektur für`VFPv3`Arm festgelegt wurde ().

  - Ein Wert im Bereich 40-49, wenn `/arch:VFPv4` festgelegt wurde.

  - Weitere Informationen finden Sie unter [/arch (Arm)](../build/reference/arch-arm.md).

- **&#95;M&#95;ARM64** Definiert als 1 für Kompilierungen, die auf 64-Bit-ARM-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95;M&#95;CEE** ist als 001 definiert, wenn eine/CLR-Compileroption [(Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) festgelegt ist. Andernfalls nicht definiert.

- **M&#95;CEE&#95;Pure &#95;** Ab Visual Studio 2015 als veraltet markiert. Wird als 001 definiert, wenn die [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- M-CEE-Sicherheit **&#95; &#95;&#95;** Ab Visual Studio 2015 als veraltet markiert. Definiert als 001, wenn die [/clr: Safe](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;FP&#95;außer** definiert als 1, wenn die Compileroption [/fp: außer](../build/reference/fp-specify-floating-point-behavior.md) oder [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;FP&#95;fast** definiert als 1, wenn die [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;FP&#95;** ist als 1 festgelegt, wenn die [/fp: precise](../build/reference/fp-specify-floating-point-behavior.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;FP&#95;Strict** ist als 1 definiert, wenn die [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;M&#95;IX86** Definiert als ganzzahliger Literalwert 600 für Kompilierungen, die auf x86-Prozessoren abzielen. Dieses Makro ist nicht für x64-oder arm-Kompilierungs Ziele definiert.

- **&#95;M&#95;IX86&#95;FP** ist als ganzzahliger Literalwert definiert, der die [/arch](../build/reference/arch-arm.md) -Compileroption angibt, die festgelegt wurde, oder die Standardeinstellung. Dieses Makro wird immer definiert, wenn es sich beim Kompilierungs Ziel um einen x86-Prozessor handelt. Andernfalls nicht definiert. Wenn definiert, lautet der Wert:

  - 0, wenn `/arch:IA32` die Compileroption festgelegt wurde.

  - 1, wenn `/arch:SSE` die Compileroption festgelegt wurde.

  - 2, wenn `/arch:SSE2`die `/arch:AVX`-, `/arch:AVX2` -oder-Compileroption festgelegt wurde. Dieser Wert ist der Standardwert, `/arch` wenn keine Compileroption angegeben wurde. Wenn `/arch:AVX` angegeben wird, wird auch das Makro **&#95; &#95;AVX&#95;** definiert. Wenn `/arch:AVX2` angegeben wird, werden sowohl  **&#95; &#95;&#95; AVX** als **&#95; &#95;auch AVX2&#95;** definiert.

  - Weitere Informationen finden Sie unter [/arch (x86)](../build/reference/arch-x86.md).

- **&#95;M&#95;x64** Definiert als ganzzahliger Literalwert 100 für Kompilierungen, die auf x64-Prozessoren abzielen. Andernfalls nicht definiert.

- **&#95;Verwaltet** Definiert als 1, wenn die [/CLR](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;MSC&#95;-Build** Definiert als Ganzzahlliteral, das das Revisionsnummern Element der Versionsnummer des Compilers enthält. Die Revisionsnummer ist das vierte Element der durch Punkte getrennten Versionsnummer. Wenn die Versionsnummer von Microsoft C/Compiler z. bC++ . 15.00.20706.01 ist, wird  **&#95;das&#95;MSC-Build** -Makro zu 1 ausgewertet. Dieses Makro wird immer definiert.

- **&#95;MSC&#95;-Erweiterungen** werden als 1 definiert, wenn die standardmäßige/Ze-Compileroption [(Spracherweiterungen aktivieren)](../build/reference/za-ze-disable-language-extensions.md) festgelegt ist. Andernfalls nicht definiert.

- **Vollständiger&#95;MSC&#95; &#95;** Definiert als Ganzzahlliteral, das die Elemente Major, Minor und Build number der Versionsnummer des Compilers codiert. Die Haupt Zahl ist das erste Element der durch Punkte getrennten Versionsnummer, die neben Nummer ist das zweite Element, und die Buildnummer ist das dritte Element. Wenn die Versionsnummer von Microsoft C/Compiler beispielsweise 15.00.20706.01C++ ist, wird das  **&#95;Full&#95;&#95;-ver** -Makro von MSC zu 150020706 ausgewertet. Geben `cl /?` Sie in der Befehlszeile ein, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.

- **&#95;MSC&#95;-ver** Definiert als Ganzzahlliteral, das die Haupt-und neben Versions Elemente der Versionsnummer des Compilers codiert. Die Haupt Zahl ist das erste Element der durch Punkte getrennten Versionsnummer, und die neben Zahl ist das zweite Element. Wenn die Versionsnummer von Microsoft C/Compiler beispielsweise 17.00.51106.1C++ lautet, wird das  **&#95;MSC&#95;-ver** -Makro zu 1700 ausgewertet. Geben `cl /?` Sie in der Befehlszeile ein, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.

   |Visual Studio-Version|**&#95;MSC&#95;-VER**|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 (7,0)|1300|
   |Visual Studio .NET 2003 (7,1)|1310|
   |Visual Studio 2005 (8,0)|1400|
   |Visual Studio 2008 (9,0)|1500|
   |Visual Studio 2010 (10,0)|1600|
   |Visual Studio 2012 (11,0)|1700|
   |Visual Studio 2013 (12,0)|1800|
   |Visual Studio 2015 (14,0)|1900|
   |Visual Studio 2017 RTW (15,0)|1910|
   |Visual Studio 2017 Version 15.3|1911|
   |Visual Studio 2017 Version 15.5|1912|
   |Visual Studio 2017 Version 15.6|1913|
   |Visual Studio 2017-Version 15.7|1914|
   |Visual Studio 2017 Version 15.8|1915|
   |Visual Studio 2017, Version 15,9|1916|
   |Visual Studio 2019 RTW (16,0)|1920|
   |Visual Studio 2019 Version 16.1|1921|
   |Visual Studio 2019 Version 16.2|1922|
   |Visual Studio 2019, Version 16,3|1923|

   Verwenden Sie den **>=** -Operator, um auf compilerreleases oder Updates in einer bestimmten Version von Visual Studio oder nach zu testen. Sie können Sie in einer bedingten Direktive verwenden,  **&#95;um&#95;MSC ver** mit dieser bekannten Version zu vergleichen. Wenn Sie über mehrere gegenseitig ausschließende Versionen verfügen, ordnen Sie Ihre Vergleiche in absteigender Reihenfolge der Versionsnummer an. Mit diesem Code wird beispielsweise auf Compiler überprüft, die in Visual Studio 2017 oder höher veröffentlicht wurden. Als nächstes überprüft er, ob Compiler in oder nach Visual Studio 2015 veröffentlicht wurden. Anschließend werden alle Compiler überprüft, die vor Visual Studio 2015 veröffentlicht wurden:

   ```cpp
   #if _MSC_VER >= 1910
   // . . .
   #elif _MSC_VER >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   Weitere Informationen finden Sie unter [Visual C++ Compiler Version](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/) im Microsoft C++ Team Blog.

- **&#95;MSVC&#95;lang** ist als Ganzzahlliteral definiert C++ , das den Sprachstandard angibt, den der Compiler als Ziel hat. Sie wird nur in Code festgelegt, C++der als kompiliert wird. Das-Makro ist der ganzzahlige Literalwert 201402l standardmäßig oder, wenn die [/Std: c++ 14](../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben wird. Das-Makro wird auf 201703l festgelegt, wenn die Compileroption [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) angegeben wird. Der Wert wird auf einen höheren, nicht angegebenen Wert festgelegt, wenn die Option [/Std: c + + Latest](../build/reference/std-specify-language-standard-version.md) angegeben wird. Andernfalls ist das Makro nicht definiert. Die  **&#95;Compileroptionen&#95;MSVC lang** und [/Std (Standard Version angeben)](../build/reference/std-specify-language-standard-version.md) sind ab Visual Studio 2015 Update 3 verfügbar.

- **&#95;&#95;MSVC&#95;-&#95;Lauf Zeit Prüfungen** werden als 1 definiert, wenn eine der [/RTC](../build/reference/rtc-run-time-error-checks.md) -Compileroptionen festgelegt ist. Andernfalls nicht definiert.

- **&#95;MSVC&#95;-traditionell** als "0" definiert, wenn die Compileroption "präprozessorübereinstimmungs Modus [/experimental: Präprozessor](../build/reference/rtc-run-time-error-checks.md) " festgelegt ist Wird standardmäßig als 1 definiert, oder wenn die [/experimental: Präprozessor-Compiler-](../build/reference/rtc-run-time-error-checks.md) Option festgelegt ist, um anzugeben, dass der herkömmliche Präprozessor bereits verwendet wird. Die Compileroption "  **&#95;herkömmliches MSVC&#95;** -Makro" und " [/experimental: präprocessor" (präprozessorkonformitätsmodus aktivieren)](../build/reference/experimental-preprocessor.md) ist ab Visual Studio 2017 Version 15,8 verfügbar.

   ```cpp
   #if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
   // Logic using the traditional preprocessor
   #else
   // Logic using cross-platform compatible preprocessor
   #endif
   ```

- **&#95;MT** Definiert als 1, wenn [/MD oder/MDD](../build/reference/md-mt-ld-use-run-time-library.md) (Multithread-DLL) oder [/MT oder/MTD](../build/reference/md-mt-ld-use-run-time-library.md) (Multithread) angegeben wird. Andernfalls nicht definiert.

- **&#95;System&#95;eigenes&#95;WCHAR&#95;T definiert** als 1, wenn die [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;OpenMP** Definiert als Ganzzahlliteral 200203, wenn die Compileroption [/OpenMP (OpenMP 2,0-Unterstützung aktivieren)](../build/reference/openmp-enable-openmp-2-0-support.md) festgelegt ist. Dieser Wert stellt das Datum der von MSVC implementierten OpenMP-Spezifikation dar. Andernfalls nicht definiert.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;Vorab&#95;** Definiert als 1, wenn die [/analyze](../build/reference/analyze-code-analysis.md) -Compileroption festgelegt ist. Andernfalls nicht definiert.

- **&#95;&#95; Zeit &#95;Stempel** Definiert als Zeichenfolgenliterale, das Datum und Uhrzeit der letzten Änderung der aktuellen Quelldatei im abgekürzten Konstanten Längen Formular enthält, das von der CRT [Asctime](../c-runtime-library/reference/asctime-wasctime.md) -Funktion zurückgegeben `Fri 19 Aug 13:32:58 2016`wird, z. b. Dieses Makro wird immer definiert.

- **&#95;VC&#95;NODEFAULTLIB** ist als 1 definiert, wenn die Compileroption [/ZL (Standard Bibliotheks Name weglassen)](../build/reference/zl-omit-default-library-name.md) festgelegt ist. Andernfalls nicht definiert.

- **&#95;WCHAR&#95;T&#95;definiert** als 1, wenn die standardmäßige [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) -Compileroption festgelegt ist. Das  **&#95;WCHAR&#95;T&#95;-definierte** Makro ist definiert, hat jedoch keinen Wert `/Zc:wchar_t-` , wenn die Compileroption festgelegt ist, und **wchar_t** wird in einer System Header Datei definiert, die im Projekt enthalten ist. Andernfalls nicht definiert.

- **&#95;Win32** Definiert als 1, wenn das Kompilierungs Ziel 32-Bit-Arm, 64-Bit Arm, x86 oder x64 ist. Andernfalls nicht definiert.

- **&#95;Win64** Definiert als 1, wenn das Kompilierungs Ziel 64-Bit-Arm oder x64 ist. Andernfalls nicht definiert.

- **&#95;WinRT&#95;-dll** ist als 1 definiert, C++ Wenn kompiliert als und sowohl [/ZW (Windows-Runtime Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) als auch [/LD-oder/ldd](../build/reference/md-mt-ld-use-run-time-library.md) -Compileroptionen festgelegt werden. Andernfalls nicht definiert.

Keine Präprozessormakros, die die ATL-oder MFC-Bibliotheksversion identifizieren, werden vom Compiler vordefiniert. ATL-und MFC-Bibliotheks Header definieren diese Versions Makros intern. Sie sind in Präprozessordirektiven, die vor der Aufnahme des erforderlichen Headers erstellt wurden, nicht definiert.

- **&#95;ATL&#95;-ver** , \<der in atldef. h definiert ist, > als Ganzzahlliteral, das die ATL-Versionsnummer codiert.

- **&#95;&#95;** Der in\<afxver_. h definierte MFC-ver > als Ganzzahlliteral, das die MFC-Versionsnummer codiert.

## <a name="see-also"></a>Siehe auch

[Makros (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)<br/>
[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)