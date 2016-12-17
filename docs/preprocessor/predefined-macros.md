---
title: "Vordefinierte Makros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_ATL_VER"
  - "__ATOM__"
  - "__AVX__"
  - "__AVX2__"
  - "_CHAR_UNSIGNED"
  - "__CLR_VER"
  - "_CONTROL_FLOW_GUARD"
  - "__COUNTER__"
  - "__cplusplus"
  - "__cplusplus_cli"
  - "__cplusplus_winrt"
  - "_CPPRTTI"
  - "_CPPUNWIND"
  - "__DATE__"
  - "_DEBUG"
  - "_DLL"
  - "__FILE__"
  - "__FUNCDNAME__"
  - "__FUNCSIG__"
  - "__FUNCTION__"
  - "_INTEGRAL_MAX_BITS"
  - "_ISO_VOLATILE"
  - "_KERNEL_MODE"
  - "__LINE__"
  - "_M_AMD64"
  - "_M_ARM"
  - "_M_ARM_ARMV7VE"
  - "_M_ARM_FP"
  - "_M_ARM64"
  - "_M_CEE"
  - "_M_CEE_PURE"
  - "_M_CEE_SAFE"
  - "_M_FP_EXCEPT"
  - "_M_FP_FAST"
  - "_M_FP_PRECISE"
  - "_M_FP_STRICT"
  - "_M_IX86"
  - "_M_IX86_FP"
  - "_M_X64"
  - "_MANAGED"
  - "_MFC_VER"
  - "_MSC_BUILD"
  - "_MSC_EXTENSIONS"
  - "_MSC_FULL_VER"
  - "_MSC_VER"
  - "_MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS"
  - "_MT"
  - "_NATIVE_WCHAR_T_DEFINED"
  - "_NO_SIZED_DEALLOCATION"
  - "_OPENMP"
  - "_PREFAST_"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED"
  - "_RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__"
  - "__STDC_HOSTED__"
  - "__STDCPP_THREADS__"
  - "__TIME__"
  - "__TIMESTAMP__"
  - "__VA_ARGS__"
  - "_VC_NODEFAULTLIB"
  - "_WCHAR_T_DEFINED"
  - "_WIN32"
  - "_WIN64"
  - "_WINRT_DLL"
  - "__func__"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeitstempel, Präprozessormakro"
  - "CL.exe-Compiler, Versionsnummer"
  - "Versionsnummern, C/C++-Compiler (cl.exe)"
  - "Makros, vordefinierte (C++)"
  - "Präprozessor-Makros"
  - "Vordefinierte Makros"
  - "_ATL_VER-Makro"
  - "__ATOM__-Makro"
  - "__AVX__-Makro"
  - "__AVX2__-Makro"
  - "_CHAR_UNSIGNED-Makro"
  - "__CLR_VER-Makro"
  - "_CONTROL_FLOW_GUARD-Makro"
  - "__COUNTER__-Makro"
  - "__cplusplus-Makro"
  - "__cplusplus_cli-Makro"
  - "__cplusplus_winrt-Makro"
  - "_CPPRTTI-Makro"
  - "_CPPUNWIND-Makro"
  - "__DATE__-Makro"
  - "_DEBUG-Makro"
  - "_DLL-Makro"
  - "__FILE__-Makro"
  - "__FUNCDNAME__-Makro"
  - "__FUNCSIG__-Makro"
  - "__FUNCTION__-Makro"
  - "_INTEGRAL_MAX_BITS-Makro"
  - "_ISO_VOLATILE-Makro"
  - "_KERNEL_MODE-Makro"
  - "__LINE__-Makro"
  - "_M_AMD64-Makro"
  - "_M_ARM-Makro"
  - "_M_ARM_ARMV7VE-Makro"
  - "_M_ARM_FP-Makro"
  - "_M_ARM64-Makro"
  - "_M_CEE-Makro"
  - "_M_CEE_PURE-Makro"
  - "_M_CEE_SAFE-Makro"
  - "_M_FP_EXCEPT-Makro"
  - "_M_FP_FAST-Makro"
  - "_M_FP_PRECISE-Makro"
  - "_M_FP_STRICT-Makro"
  - "_M_IX86-Makro"
  - "_M_IX86_FP-Makro"
  - "_M_X64-Makro"
  - "_MANAGED-Makro"
  - "_MFC_VER-Makro"
  - "_MSC_BUILD-Makro"
  - "_MSC_EXTENSIONS-Makro"
  - "_MSC_FULL_VER-Makro"
  - "_MSC_VER-Makro"
  - "_MSVC_LANG-Makro"
  - "__MSVC_RUNTIME_CHECKS-Makro"
  - "_MT-Makro"
  - "_NATIVE_WCHAR_T_DEFINED-Makro"
  - "_NO_SIZED_DEALLOCATION-Makro"
  - "_OPENMP-Makro"
  - "_PREFAST_-Makro"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED-Makro"
  - "_RTC_CONVERSION_CHECKS_ENABLED-Makro"
  - "__STDC__-Makro"
  - "__STDC_HOSTED__-Makro"
  - "__STDCPP_THREADS__-Makro"
  - "__TIME__-Makro"
  - "__TIMESTAMP__-Makro"
  - "__VA_ARGS__-Makro"
  - "_VC_NODEFAULTLIB-Makro"
  - "_WCHAR_T_DEFINED-Makro"
  - "_WIN32-Makro"
  - "_WIN64-Makro"
  - "_WINRT_DLL-Makro"
  - "__func__-Bezeichner"
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
caps.latest.revision: 75
caps.handback.revision: "75"
ms.author: "corob"
manager: "ghogen"
---
# Vordefinierte Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C++-Compiler definiert bestimmte Präprozessormakros, je nach Sprache (C oder C++), das Kompilierungsziel und die ausgewählten Compileroptionen.  
  
 Visual C++ unterstützt die erforderlichen vordefinierten Präprozessormakros durch ANSI/ISO C99-Standard und der ISO C ++ 14-standard angegeben. Die Implementierung unterstützt auch mehrere weitere Microsoft-spezifische Präprozessormakros. Einige Makros werden nur für bestimmte Buildumgebungen oder Compileroptionen definiert. Sofern nicht angegeben, werden die Makros, die während einer Übersetzungseinheit definiert, als ob sie als angegeben wurden **/d** Argumente für Compiler-Option. Wenn definiert, werden die Makros vom Präprozessor vor der Kompilierung auf die angegebenen Werte erweitert. Die vordefinierten Makros akzeptieren keine Argumente und können nicht neu definiert werden.  
  
## <a name="standard-predefined-identifier"></a>Vordefinierte Standardbezeichner  
 Der Compiler unterstützt diese vordefinierten Bezeichner gemäß ISO C99 und ISO C ++ 11.  
  
-   **__func\_\_** den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion als eine Funktion lokalen `static``const` Array von `char`.  
  
    ```cpp  
    void example(){  
        printf("%s\n", __func__);  
    } // prints "example"  
    ```  
  
## <a name="standard-predefined-macros"></a>Standard vordefinierte Makros  
 Der Compiler unterstützt diesen vordefinierten Makros, die durch den ISO C99 und ISO C ++ 14-Standards angegeben.  
  
-   **__cplusplus** als literal Ganzzahl definiert werden, wenn der Übersetzungseinheit als C++ kompiliert wird. Andernfalls nicht definiert.  
  
-   **__DATE\_\_** das kompilierungsdatum der aktuellen Quelldatei. Das Datum ist eine Konstante Länge Zeichenfolgenliteral des Formats *Mmm Dd Yyyy*. Der Name des Monats *Mmm* ist identisch mit der abgekürzte Name des Monats in Daten, die von der C-Laufzeitbibliothek generiert [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Das erste Zeichen des Datums *Dd* ein Leerzeichen ist, wenn der Wert kleiner als 10 ist. Dieses Makro wird immer definiert.  
  
-   **__FILE\_\_** den Namen der aktuellen Quelldatei. **__FILE\_\_** wird erweitert, um ein Zeichenfolgenliteral. Um sicherzustellen, dass der vollständige Pfad zur Datei angezeigt wird, verwenden [/FC (vollständiger Pfad der Quellcodedatei in Diagnose)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Dieses Makro wird immer definiert.  
  
-   **__LINE\_\_** als ganze Zahl Zeilennummer in der aktuellen Quelldatei definiert. Der Wert des der **__LINE\_\_** Makro kann geändert werden, mithilfe einer `#line` Richtlinie. Dieses Makro wird immer definiert.  
  
-   **__STDC\_\_** als 1 definiert wird, nur, wenn als C kompiliert und die [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption angegeben wird. Andernfalls nicht definiert.  
  
-   **__STDC_HOSTED\_\_** als 1 definiert wird, ist die Implementierung einer *gehostet Implementierung*, eine, die die gesamte erforderliche Standardbibliothek unterstützt. Andernfalls definiert als 0.  
  
-   **__STDCPP_THREADS\_\_** als 1 definiert wird, nur, wenn ein Programm mehrere Ausführungsthreads haben kann und als C++ kompiliert. Andernfalls nicht definiert.  
  
-   **__TIME\_\_** die Uhrzeit der Übersetzung der vorverarbeiteten Übersetzungseinheit. Die Zeit ist eine Zeichenfolge Zeichenfolgenliteral des Formats *hh: mm:*, die von C-Laufzeitbibliothek zurückgegebene Uhrzeit identisch [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion. Dieses Makro wird immer definiert.  
  
## <a name="microsoft-specific-predefined-macros"></a>Microsoft-spezifische vordefinierte Makros  
 Microsoft Visual C++ unterstützt diesen zusätzlichen vordefinierten Makros.  
  
-   **__ATOM\_\_** als 1 bei definiert die [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) (Compileroption) festgelegt ist und das compilerziel X86 oder X64. Andernfalls nicht definiert.  
  
-   **__AVX\_\_** als 1 bei definiert die [/arch: AVX](../build/reference/arch-x86.md) oder [/arch: avx2](../build/reference/arch-x86.md) Compileroptionen festgelegt und das compilerziel X86 oder X64. Andernfalls nicht definiert.  
  
-   **__AVX2\_\_** als 1 bei definiert die [/arch: avx2](../build/reference/arch-x86.md) (Compileroption) festgelegt ist und das compilerziel X86 oder X64. Andernfalls nicht definiert.  
  
-   **_CHAR_UNSIGNED** definiert als 1, wenn der Standardwert `char` Typ ohne Vorzeichen ist. Dadurch wird festgelegt, wenn die [/j (standardmäßig Typ unsigned Char)](../build/reference/j-default-char-type-is-unsigned.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **__CLR_VER** als ein Ganzzahlliteral, das die Version der common Language Runtime zum Zeitpunkt der Kompilierung der Anwendung, definiert. Der Wert ist in der Form codiert `Mmmbbbbb`, wobei `M` die Hauptversion der Laufzeit `mm` ist die Nebenversionsnummer der Laufzeit und `bbbbb` die Buildnummer. **__CLR_VER** wird definiert, wenn die [/CLR](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
    ```cpp  
    // clr_ver.cpp  
    // compile with: /clr  
    using namespace System;  
    int main() {  
       Console::WriteLine(__CLR_VER);  
    }  
    ```  
  
-   **_CONTROL_FLOW_GUARD** als 1 bei definiert die [/guard:cf (aktivieren Control Flow schützen)](../build/reference/guard-enable-control-flow-guard.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **__COUNTER\_\_** Expands ein Ganzzahlliteral, das bei 0 beginnt und jedes Mal, wenn sie in einer Quelldatei verwendet wird um 1 erhöht oder eingeschlossenen Headern der Quelldatei. **__COUNTER\_\_** speichert den Zustand beim Verwenden vorkompilierter Header. Dieses Makro wird immer definiert.  
  
     Dieses Beispiel verwendet `__COUNTER__` um eindeutige Bezeichner drei verschiedenen Objekten desselben Typs zuzuweisen. Die `exampleClass` Konstruktor akzeptiert eine ganze Zahl als Parameter. In `main`, die Anwendung drei Objekte des Typs deklariert `exampleClass`, wobei `__COUNTER__` als eindeutigen Bezeichner-Parameter:  
  
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
  
-   **"__cplusplus_cli"** als Integer-Literalwert 200406 bei Kompilierung als C++ definiert und die [/CLR](../build/reference/clr-common-language-runtime-compilation.md), [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md), oder [/clr: safe](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert. Wenn definiert, **__cplusplus_cli** ist während der Übersetzungseinheit wirksam.  
  
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
  
-   **__cplusplus_winrt** als Integer-Literalwert 201009 bei Kompilierung als C++ definiert und die [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_CPPRTTI** definiert als 1, wenn die [/GR (Enable Run-Time Type Information)](../build/reference/gr-enable-run-time-type-information.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_CPPUNWIND** als 1 definiert, wenn mindestens eine der [/GX (Ausnahmebehandlung aktivieren)](../build/reference/gx-enable-exception-handling.md), [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md), oder [/EH (Exception Handling Model)](../build/reference/eh-exception-handling-model.md) Compileroptionen festgelegt werden. Andernfalls nicht definiert.  
  
-   **_DEBUG** definiert als 1 bei der ["/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), oder [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_DLL** definiert als 1 bei der [/MD](../build/reference/md-mt-ld-use-run-time-library.md) oder [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) Compileroption (Multithreaded DLL) festgelegt ist. Andernfalls nicht definiert.  
  
-   **__FUNCDNAME\_\_** definiert als ein Zeichenfolgenliteral, das enthält die [ergänzten Namen](../build/reference/decorated-names.md) der einschließenden Funktion. Das Makro wird nur innerhalb einer Funktion definiert. Die **__FUNCDNAME\_\_** Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption.  
  
     Dieses Beispiel verwendet die `__FUNCDNAME__`, `__FUNCSIG__`, und `__FUNCTION__` Makros um Funktionsinformationen anzuzeigen.  
  
     [!CODE [NVC_Predefined_Macros_Examples#1](../CodeSnippet/VS_Snippets_Cpp/nvc_predefined_macros_examples#1)]  
  
-   **__FUNCSIG\_\_** definiert als ein Zeichenfolgenliteral, das die Signatur der einschließenden Funktion enthält. Das Makro wird nur innerhalb einer Funktion definiert. Die **__FUNCSIG\_\_** Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Wenn für ein 64-Bit-Ziel kompiliert wird, ist die Aufrufkonvention `__cdecl` standardmäßig. Ein Beispiel für die Verwendung, finden Sie unter der `__FUNCDNAME__` Makro.  
  
-   **__FUNCTION\_\_** definiert als ein Zeichenfolgenliteral, das den nicht ergänzten Namen der einschließenden Funktion enthält. Das Makro wird nur innerhalb einer Funktion definiert. Die **__FUNCTION\_\_** Makro wird nicht erweitert, wenn Sie verwenden die [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) oder [/p](../build/reference/p-preprocess-to-a-file.md) -Compileroption. Ein Beispiel für die Verwendung, finden Sie unter der `__FUNCDNAME__` Makro.  
  
-   **_INTEGRAL_MAX_BITS** benutzerdefinierte literal Ganzzahlwert 64, die maximale Größe (in Bits) für einen ganzzahligen Typ mit nicht-Vektor. Dieses Makro wird immer definiert.  
  
    ```cpp  
    // integral_max_bits.cpp  
    #include <stdio.h>  
    int main() {  
       printf("%d\n", _INTEGRAL_MAX_BITS);  
    }  
    ```  
  
-   **__INTELLISENSE\_\_** definiert, wie 1, während ein IntelliSense-Compiler in Visual Studio-IDE übergeben. Andernfalls nicht definiert. Sie können dieses Makro verwenden, um Code zu schützen, die IntelliSense-Compiler nicht verstehen, oder verwenden, um das Umschalten zwischen der Build und die IntelliSense-Compiler. Weitere Informationen finden Sie unter [Tipps zur Problembehandlung für IntelliSense Langsamkeit](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/).  
  
-   **_ISO_VOLATILE** definiert als 1, wenn die [Sprachstandard](../build/reference/volatile-volatile-keyword-interpretation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_KERNEL_MODE** definiert als 1, wenn die [/Kernel (erstellen Kernel-Modus binär)](../build/reference/kernel-create-kernel-mode-binary.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_AMD64** wie das Ganzzahlliteral Wert 100 für Kompilierungen, X64-Prozessoren definiert. Andernfalls nicht definiert.  
  
-   **_M_ARM** definiert als die Integer-Literalwert 7 für Kompilierungen, ARM-Prozessoren abzielen. Andernfalls nicht definiert.  
  
-   **_M_ARM_ARMV7VE** als 1 bei definiert die [/arch: armv7ve](../build/reference/arch-arm.md) Compileroption für Kompilierungen, die ARM-Prozessoren als Ziel festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_ARM_FP** definiert ein Integer-literal-Wert, der gibt an [/arch](../build/reference/arch-arm.md) Compileroption wurde festgelegt, wenn das Kompilierungsziel ein ARM-Prozessor ist. Andernfalls nicht definiert.  
  
    -   Im Bereich 30-39 ohne Festlegung **/arch** ARM-Option angegeben wurde, dass die standardmäßige Architektur für ARM festgelegt wurde (`VFPv3`).  
  
    -   Im Bereich 40-49, wenn **/arch: vfpv4** festgelegt wurde.  
  
    -   Finden Sie unter [/arch (ARM)](../build/reference/arch-arm.md) für Weitere Informationen.  
  
-   **_M_ARM64** definiert als 1 für Kompilierungen, 64-Bit-ARM-Prozessoren abzielen. Andernfalls nicht definiert.  
  
-   **_M_CEE** als definiert, 001 Wenn alle [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_CEE_PURE** als definiert, wenn 001 der [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_CEE_SAFE** als definiert, wenn 001 der [/clr: safe](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_FP_EXCEPT** definiert als 1, wenn die [/fp: außer](../build/reference/fp-specify-floating-point-behavior.md) oder [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_FP_FAST** definiert als 1, wenn die [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_FP_PRECISE** definiert als 1, wenn die [/fp: präzise](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_FP_STRICT** definiert als 1, wenn die [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_M_IX86** wie das Ganzzahlliteral Wert von 600 für Kompilierungen, X86-Prozessoren definiert. Dieses Makro wird nicht für X64 oder ARM-Kompilierung Ziele definiert.  
  
-   **_M_IX86_FP** definiert als ein Zeichenfolgenliteral Integer-Wert, der angibt der [/arch](../build/reference/arch-arm.md) -Compileroption, die Gruppe oder der Standard wurde. Dieses Makro wird immer definiert, wird das Kompilierungsziel einer X86 Prozessor. Andernfalls nicht definiert. Wenn definiert, lautet der Wert:  
  
    -   0, wenn die **/arch:IA32** (Compileroption) festgelegt wurde.  
  
    -   1, wenn die **neben** (Compileroption) festgelegt wurde.  
  
    -   2, wenn die **/arch: SSE2**, **/arch: AVX** oder **/arch: avx2** (Compileroption) festgelegt wurde. Dieser Wert ist der Standardwert, wenn ein **/arch** Compileroption wurde nicht angegeben. Wenn **/arch: AVX** angegeben wird, das Makro **__AVX\_\_** ebenfalls definiert ist. Wenn **/arch: avx2** angegeben wird, beide **__AVX\_\_** und **__AVX2\_\_** sind ebenfalls definiert.  
  
    -   Finden Sie unter [/arch (x86)](../build/reference/arch-x86.md) Weitere Informationen.  
  
-   **_M_X64** wie das Ganzzahlliteral Wert 100 für Kompilierungen, X64-Prozessoren definiert. Andernfalls nicht definiert.  
  
-   **_MANAGED** definiert als 1 bei der [/CLR](../build/reference/clr-common-language-runtime-compilation.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_MSC_BUILD** definiert als ein Ganzzahlliteral, das die Revision Number-Element der Versionsnummer des Compilers enthält. Die Revisionsnummer ist das vierte Element der durch Punkte getrennten Versionsnummer. Die Versionsnummer des Visual C++-Compilers beispielsweise "15.00.20706.01" ist, die **_MSC_BUILD** -Makro in 1 ausgewertet. Dieses Makro wird immer definiert.  
  
-   **_MSC_EXTENSIONS** definiert als 1, wenn die [/Ze (Spracherweiterungen aktivieren)](../build/reference/za-ze-disable-language-extensions.md) (Compileroption) festgelegt ist, wird die Standardeinstellung. Andernfalls nicht definiert.  
  
-   **_MSC_FULL_VER** definiert als ein Ganzzahlliteral, die codiert die Hauptversionsnummer, Nebenversionsnummer und Buildnummer Anzahl Elemente der Versionsnummer des Compilers. Die Nummer der Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer und die Build-Nummer ist das dritte Element die Nummer die Nebenversion ist das zweite Element. Die Versionsnummer des Visual C++-Compilers beispielsweise "15.00.20706.01" ist, die **_MSC_FULL_VER** Makro ergibt 150020706 ausgewertet. Geben Sie **cl /?** in der Befehlszeile, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.  
  
-   **_MSC_VER** definiert als ein Ganzzahlliteral, das die Haupt- und Nebenversionsnummern Anzahl Elemente der Versionsnummer des Compilers codiert. Die Nummer der Hauptversion ist das erste Element der durch Punkte getrennten Versionsnummer und die Nebenversionsnummer ist das zweite Element. Die Versionsnummer des Visual C++-Compilers beispielsweise "17.00.51106.1" ist, die **_MSC_VER** Makro zu 1700 ausgewertet wird. Geben Sie **cl /?** in der Befehlszeile, um die Versionsnummer des Compilers anzuzeigen. Dieses Makro wird immer definiert.  
  
-   **_MSVC_LANG** als ein Ganzzahlliteral, der angibt, den C++-Sprache-Standard der Compiler das Ziel definiert. Wenn als C++ kompiliert wird, ist das Makro der Integer-Literalwert 201402, wenn die [/std:c ++ 14](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) Compileroption ist, oder indem und zu einer höheren festgelegt ist, nicht angegeben-Wert, wenn die [/std:c ++ neueste](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) (Compileroption) festgelegt ist. Andernfalls ist das Makro nicht definiert. Die **_MSVC_LANG** Makro und [/std (Geben Sie standardmäßige Sprachversion)](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) ab, die in Visual Studio 2015 Update 3 verfügbar sind.  
  
-   **__MSVC_RUNTIME_CHECKS** definiert als 1, wenn eine von der [/RTC](../build/reference/rtc-run-time-error-checks.md) Compileroptionen festgelegt ist. Andernfalls nicht definiert.  
  
-   **_MT** definiert als 1 bei [/MD oder/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded DLL) oder [/MT oder/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (Multithreaded) angegeben wurde. Andernfalls nicht definiert.  
  
-   **_NATIVE_WCHAR_T_DEFINED** definiert als 1 bei der [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_OPENMP** als ganze Zahl literal 200203, das Datum der OpenMP-Spezifikation, die von Visual C++ implementierte darstellt, wenn die [/OpenMP (Aktivieren der OpenMP 2.0-Unterstützung)](../build/reference/openmp-enable-openmp-2-0-support.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
    ```cpp  
    // _OPENMP_dir.cpp  
    // compile with: /openmp   
    #include <stdio.h>   
    int main() {  
       printf("%d\n", _OPENMP);  
    }  
    ```  
  
-   **_PREFAST\_** als 1 bei definiert die [/ analyze](../build/reference/analyze-code-analysis.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **__TIMESTAMP\_\_** definiert als ein Zeichenfolgenliteral, das Datum und Uhrzeit der letzten Änderung der aktuellen Quelldatei, in Form abgekürzten, Konstante Länge zurückgegeben, die von der C-Laufzeitbibliothek enthält [Asctime](../c-runtime-library/reference/asctime-wasctime.md) Funktion, z. B. `Fri 19 Aug 13:32:58 2016`. Dieses Makro wird immer definiert.  
  
-   **_VC_NODEFAULTLIB** definiert als 1 bei der [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md) (Compileroption) festgelegt ist. Andernfalls nicht definiert.  
  
-   **_WCHAR_T_DEFINED** definiert als 1 bei Standard [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) (Compileroption) festgelegt ist. Die **_WCHAR_T_DEFINED** Makro definiert ist, aber keinen Wert besitzt, wenn die **/Zc:wchar_t-** (Compileroption) festgelegt ist, und `wchar_t` in einer systemheaderdatei in Ihrem Projekt definiert ist. Andernfalls nicht definiert.  
  
-   **_WIN32** definiert als 1 wird das Kompilierungsziel 32-Bit-ARM, 64-Bit-ARM X86, oder x 64. Andernfalls nicht definiert.  
  
-   **_WIN64** bei der Kompilierung Target 64-Bit-ARM oder X64 ist als 1 definiert. Andernfalls nicht definiert.  
  
-   **_WINRT_DLL** definiert, wie C++ und sowohl als 1 bei kompiliert [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md) und [/ld oder "/ LDD"](../build/reference/md-mt-ld-use-run-time-library.md) Compileroptionen festgelegt werden. Andernfalls nicht definiert.  
  
 Bestimmt die ATL- oder MFC-Bibliotheksversion Präprozessormakros werden vom Compiler nicht vordefiniert. Diese Makros werden in den Headern für die Bibliothek definiert, damit sie in den Präprozessordirektiven nicht definiert sind, bevor die erforderlichen Header enthalten ist.  
  
-   **_ATL_VER** als ein Ganzzahlliteral, das die ATL-Versionsnummer codiert in \< atldef.h > definiert.  
  
-   **_MFC_VER** als ein Ganzzahlliteral, das die MFC-Versionsnummer codiert in \< afxver_.h > definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros (C/C++)](../preprocessor/macros-c-cpp.md)   
 [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md)   
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)