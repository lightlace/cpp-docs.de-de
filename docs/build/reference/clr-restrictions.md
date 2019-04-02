---
title: Einschränkungen für "/clr"
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
ms.openlocfilehash: 21b7ead553871854c73021756eb2086f9e6e7393
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777817"
---
# <a name="clr-restrictions"></a>Einschränkungen für "/clr"

Beachten Sie die folgenden Einschränkungen für die Verwendung von **"/ CLR"**:

- In einem strukturierten Ausnahmehandler, es gibt Einschränkungen bei der Verwendung `_alloca` beim Kompilieren mit **"/ CLR"**. Weitere Informationen finden Sie unter [_alloca](../../c-runtime-library/reference/alloca.md).

- Die Verwendung der fehlerprüfung zur Laufzeit ist nicht gültig sein und **"/ CLR"**. Weitere Informationen finden Sie unter [Vorgehensweise: Use Native Run-Time Checks (Verwenden von nativen Laufzeitüberprüfungen)](/visualstudio/debugger/how-to-use-native-run-time-checks).

- Wenn **"/ CLR"** wird verwendet, um ein Programm zu kompilieren, das nur C++-Standardsyntax verwendet, die folgenden Richtlinien gelten für die Verwendung von Inlineassembly:

  - Inline-Assemblycode, das Wissen des systemeigenen Stapellayouts wird davon ausgegangen, Aufrufkonventionen außerhalb der aktuellen Funktion oder eines anderen Low-Level-Informationen über den Computer Falls fehlschlagen, die Kenntnisse, die dem Stapelrahmen für eine verwaltete Funktion angewendet wird. Funktionen, die Inline-Assemblycode werden als nicht verwalteter Funktionen generiert, als ob sie in einem separaten Modul platziert wurden, die ohne kompiliert wurde **"/ CLR"**.

  - Inline-Assemblycode in Funktionen, die Kopie erstellt Funktionsparameter zu übergeben, wird nicht unterstützt.

- Die [Vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md) kann nicht aufgerufen werden, von einem Programm mit kompiliert **"/ CLR"**.

- Die [naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) -Modifizierer wird unter/CLR ignoriert.

- Die Translator-Funktion festlegen, indem [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) wirkt sich nur abfängt in nicht verwaltetem Code. Finden Sie unter [Exception Handling](../../extensions/exception-handling-cpp-component-extensions.md) für Weitere Informationen.

- Der Vergleich der Funktionszeiger ist nicht zulässig, unter **"/ CLR"**.

- Die Verwendung von Funktionen ohne vollständige Prototypen ist nicht zulässig, unter **"/ CLR"**.

- Die folgenden Compileroptionen werden nicht unterstützt, mit **"/ CLR"**:

  - **/ EHsc** und **/EHs** (**"/ CLR"** impliziert **/EHa** (finden Sie unter [/EH (Ausnahmebehandlungsmodell)](eh-exception-handling-model.md))

  - **/ fp: strict** und **/fp: mit Ausnahme von** (finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](fp-specify-floating-point-behavior.md))

  - [/Zd](z7-zi-zi-debug-information-format.md)

  - [/Gm](gm-enable-minimal-rebuild.md)

  - [/MT](md-mt-ld-use-run-time-library.md)

  - [/RTC](rtc-run-time-error-checks.md)

  - [/ZI](z7-zi-zi-debug-information-format.md)

- Die Kombination der `_STATIC_CPPLIB` Präprozessordefinition (`/D_STATIC_CPPLIB`) und die **"/ CLR"** Compileroption wird nicht unterstützt. Dies rührt daher, dass die Definition würde Ihre Anwendung verknüpfen Sie mit der statische Multithread C++-Standardbibliothek, die nicht unterstützt wird. Weitere Informationen finden Sie unter den [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](md-mt-ld-use-run-time-library.md) Thema.

- Bei Verwendung **"/ Zi"** mit **"/ CLR"**, stehen Sie auf die Leistung auswirken. Weitere Informationen finden Sie unter ["/ Zi"](z7-zi-zi-debug-information-format.md).

- Ein Breitzeichen an einen .NET Framework übergeben Routine ausgeben, ohne auch [/Zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) oder ohne Umwandlung des Zeichens in `__wchar_t` bewirkt, dass die Ausgabe als eine `unsigned short int`. Zum Beispiel:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/ GS](gs-buffer-security-check.md) wird ignoriert, wenn die Kompilierung mit **"/ CLR"**, wenn eine Funktion unter `#pragma` [nicht verwalteten](../../preprocessor/managed-unmanaged.md) oder die Funktion in systemeigenen Code kompiliert werden muss, in diesem Fall generiert der Compiler Warnung C4793, die standardmäßig deaktiviert ist.

- Finden Sie unter [/Entry](entry-entry-point-symbol.md) Funktion Signatur Anforderungen einer verwalteten Anwendung.

- Anwendungen mit kompiliert **/OpenMP** und **"/ CLR"** kann nur in eine einzelne Appdomain-Prozess ausgeführt werden.  Finden Sie unter [/OpenMP (Aktivieren der OpenMP 2.0-Unterstützung)](openmp-enable-openmp-2-0-support.md) für Weitere Informationen.

- Funktionen, die eine Variable Anzahl von Argumenten (Varargs) verwenden, werden als native Funktionen generiert werden. Alle verwalteten Datentypen in die Variable Argumentlisten Position werden in native Typen gemarshallt werden. Beachten Sie, dass <xref:System.String?displayProperty=fullName> tatsächlich ein Breitzeichen-Zeichenfolgen sind, aber sie Einzelbyte-Zeichenfolgen gemarshallt werden. Daher ist ein Printf-Spezifizierer %S (Wchar_t *), wird er in eine Zeichenfolge %s stattdessen gemarshallt.

- Wenn das Va_arg-Makro verwenden, erhalten Sie möglicherweise unerwartete Ergebnisse beim Kompilieren mit **/CLR: pure**. Weitere Informationen finden Sie unter [Va_arg, Va_copy, Va_end, Va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Code, der "rein" oder "sicher" sein muss portiert werden soll, um C#.

- Rufen Sie nicht, aus verwaltetem Code, der alle Funktionen, die den Stapel zum Abrufen von Informationen zu den Parametern (Funktionsargumente;) zu durchlaufen die P/Invoke-Ebene bewirkt, dass Informationen weiter unten im Stapel werden.  Kompilieren Sie z. B. nicht Proxy/Stub mit **"/ CLR"**.

- Funktionen für verwalteten Code möglichst kompiliert werden, aber nicht alle C++-Konstrukte zu verwaltetem Code übersetzt werden können.  Diese Ermittlung erfolgt auf Basis von Funktion. Wenn Sie einen beliebigen Teil einer Funktion, die an verwalteten Code konvertiert werden kann, wird die gesamte Funktion stattdessen in systemeigenen Code konvertiert werden. Die folgenden Fälle verhindert, dass den Compiler Generieren von verwaltetem Code.

  - Vom Compiler generierter Thunks oder Hilfsfunktionen. Systemeigene Thunks werden für jeden Funktionsaufruf über einen Funktionszeiger, einschließlich der virtuellen Funktionsaufrufe generiert.

  - Dieser Aufruf funktioniert `setjmp` oder `longjmp`.

  - Funktionen, die bestimmte systeminternen Routinen zu verwenden, um Computerressourcen direkt zu bearbeiten. Z. B. die Verwendung von `__enable` und `__disable`, `_ReturnAddress` und `_AddressOfReturnAddress`, oder multimedia systeminterne Funktionen werden alle Ergebnis in systemeigenem Code.

  - Funktionen, führen Sie die `#pragma unmanaged` Richtlinie. (Beachten Sie, dass das Gegenteil, `#pragma managed`, wird ebenfalls unterstützt.)

  - Eine Funktion, die Verweise auf enthält-ausgerichtete Typen, d. h. mithilfe von Typen deklariert `__declspec(align(...))`.

## <a name="see-also"></a>Siehe auch

- [/clr (Common Language Runtime-Kompilierung)](clr-common-language-runtime-compilation.md)
