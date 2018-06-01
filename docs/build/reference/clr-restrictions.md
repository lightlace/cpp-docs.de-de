---
title: / CLR Einschränkungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34d21939f51fc3d4800d5cdd887b283b7e690db6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704268"
---
# <a name="clr-restrictions"></a>Einschränkungen für "/clr"

Beachten Sie die folgenden Einschränkungen für die Verwendung von **"/ CLR"**:

- In einem strukturierten Ausnahmehandler stehen die folgenden Einschränkungen bei der Verwendung `_alloca` beim Kompilieren mit **"/ CLR"**. Weitere Informationen finden Sie unter [_alloca](../../c-runtime-library/reference/alloca.md).

- Die Verwendung von Fehlern der fehlerprüfung zur Laufzeit ist nicht gültig, wenn **"/ CLR"**. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von systemeigenen Laufzeitprüfungen](/visualstudio/debugger/how-to-use-native-run-time-checks).

- Wenn **"/ CLR"** wird verwendet, um ein Programm zu kompilieren, nur C++-Standardsyntax verwendet, die folgenden Richtlinien gelten für die Verwendung von Inlineassemblys:

  - Inline-Assemblycode, die Kenntnisse in den systemeigenen Stapellayout annimmt, Aufrufkonventionen außerhalb der aktuellen Funktion oder eines anderen Basisinformationen über den Computer wenn möglicherweise ein Fehler, die Wissensdatenbank auf den Stapelrahmen für eine verwaltete Funktion angewendet wird. Funktionen, die mit Inline-Assemblycode werden als nicht verwaltete Funktionen generiert, als ob sie in einem separaten Modul gespeichert wurden, die ohne kompiliert wurde **"/ CLR"**.

  - Inline-Assemblycode in Funktionen, die Kopie erstellt Funktionsparameter übergeben wird nicht unterstützt.

- Die [Vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md) kann nicht aufgerufen werden, aus einem Programm kompiliert mit **"/ CLR"**.

- Die [naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) Modifizierer wird unter/CLR ignoriert.

- Die Translator-Funktion festlegen, indem [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) wirkt sich nur fängt in nicht verwaltetem Code. Finden Sie unter [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md) für Weitere Informationen.

- Beim Vergleich von Funktionszeigern darf nicht unter **"/ CLR"**.

- Die Verwendung von Funktionen ohne vollständige Prototypen darf nicht unter **"/ CLR"**.

- Die folgenden Compileroptionen werden nicht unterstützt, mit **"/ CLR"**:

  - **/ EHsc** und **/EHs** (**"/ CLR"** impliziert **/EHa** (siehe [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md))

  - **/ fp: strict** und **/fp: außer** (siehe [/fp (Festlegen von Floating-Verhalten)](../../build/reference/fp-specify-floating-point-behavior.md))

  - [/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)

  - [/Gm](../../build/reference/gm-enable-minimal-rebuild.md)

  - [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)

  - [/RTC](../../build/reference/rtc-run-time-error-checks.md)

  - [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)

- Die Kombination der `_STATIC_CPPLIB` Präprozessordefinition (`/D_STATIC_CPPLIB`) und die **"/ CLR"** (Compileroption) wird nicht unterstützt. Dies rührt daher, dass die Definition würde die Anwendung zur Verknüpfung mit der Statische multithreaded C++-Standardbibliothek, die nicht unterstützt wird. Weitere Informationen finden Sie unter der [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) Thema.

- Bei Verwendung **/Zi** mit **"/ CLR"**, stehen Sie Auswirkungen auf die Leistung. Weitere Informationen finden Sie unter [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).

- Übergeben ein Breitzeichen an einen .NET Framework Routine ohne Ausgabe [/Zc: wchar_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) oder ohne Umwandlung des Zeichens in `__wchar_t` führt dazu, dass die Ausgabe als ein `unsigned short int`. Zum Beispiel:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/ GS](../../build/reference/gs-buffer-security-check.md) wird ignoriert, wenn die Kompilierung mit **"/ CLR"**, es sei denn, eine Funktion unterliegt `#pragma` [nicht verwalteten](../../preprocessor/managed-unmanaged.md) oder wenn die Funktion in systemeigenen kompiliert werden muss, in diesem Fall generiert der Compiler Warnung C4793, das standardmäßig deaktiviert ist.

- Finden Sie unter [/Entry](../../build/reference/entry-entry-point-symbol.md) Funktion Signatur Anforderungen von einer verwalteten Anwendung.

- Anwendungen mit kompiliert **/OpenMP** und **"/ CLR"** kann nur in einem einzelnen Appdomain-Prozess ausgeführt werden.  Finden Sie unter [/OpenMP (Aktivieren der OpenMP 2.0-Unterstützung)](../../build/reference/openmp-enable-openmp-2-0-support.md) für Weitere Informationen.

- Funktionen, die eine Variable Anzahl von Argumenten (Varargs) akzeptieren, werden als systemeigene Funktionen generiert. Alle verwalteten Datentypen in der Variablen Argumentposition werden in systemeigenen Typen gemarshallt werden. Beachten Sie, dass <xref:System.String?displayProperty=fullName> Typen sind tatsächlich Breitzeichen-Zeichenfolgen, aber diese Einzelbyte-Zeichenfolgen gemarshallt werden. Daher ist ein Printf-Spezifizierer %S (Wchar_t *), wird er in eine Zeichenfolge %s stattdessen gemarshallt.

- Wenn das Makro Va_arg verwenden, erhalten Sie möglicherweise unerwartete Ergebnisse beim Kompilieren mit **/CLR: pure**. Weitere Informationen finden Sie unter [Va_arg, Va_copy, Va_end, Va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Code, der "rein" oder "sicheren" sein muss, sollten zu C#-portiert werden.

- Rufen Sie nicht, aus verwaltetem Code, der alle Funktionen, die den Stapel, um die Parameterinformationen (Funktionsargumente) abzurufen, führt die P/Invoke-Ebene bewirkt, dass Informationen weiter unten im Stapel werden.  Kompilieren Sie z. B. nicht Proxy/Stub mit **"/ CLR"**.

- Funktionen für verwalteten Code nach Möglichkeit werden kompiliert, aber nicht alle C++-Konstrukte können in verwalteten Code übersetzt werden.  Diese Feststellung erfolgt auf Basis von Funktion. Wenn Sie einen beliebigen Teil einer Funktion in verwaltetem Code konvertiert werden kann, wird die gesamte Funktion stattdessen in systemeigenen Code konvertiert werden. Die folgenden Fällen können Sie verhindern, dass den Compiler Generieren von verwaltetem Code.

  - Vom Compiler generierte Thunks oder Hilfsfunktionen. Systemeigene Thunks werden für jeden Funktionsaufruf durch einen Funktionszeiger, einschließlich virtuelle Funktionsaufrufe generiert.

  - Dieser Aufruf funktioniert `setjmp` oder `longjmp`.

  - Funktionen, mit denen bestimmte systeminternen Routinen um Computerressourcen direkt zu bearbeiten. Beispielsweise die Verwendung von `__enable` und `__disable`, `_ReturnAddress` und `_AddressOfReturnAddress`, oder multimedia systeminterne Funktionen werden alle Ergebnis in systemeigenem Code.

  - Funktionen, führen Sie die `#pragma unmanaged` Richtlinie. (Beachten Sie, dass das Gegenteil `#pragma managed`, wird ebenfalls unterstützt.)

  - Eine Funktion, die Verweise auf enthält ausgerichtet Typen, d. h. Typen deklariert mit `__declspec(align(...))`.

## <a name="see-also"></a>Siehe auch

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)
