---
title: "Einschr&#228;nkungen f&#252;r &quot;/clr&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Beschränkungen"
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# Einschr&#228;nkungen f&#252;r &quot;/clr&quot;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beachten Sie die folgenden Einschränkungen der Verwendung von **\/clr**:  
  
-   In einem strukturierte Ausnahmehandler liegen beim Kompilieren mit **\/clr** Einschränkungen für die Verwendung von `_alloca` vor.  Weitere Informationen finden Sie unter [\_alloca](../../c-runtime-library/reference/alloca.md).  
  
-   Die Verwendung von Laufzeitüberprüfungen mit **\/clr** ist nicht zulässig.  Weitere Informationen finden Sie unter [Laufzeitfehlerüberprüfungen](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
-   Wenn **\/clr** zum Kompilieren eines Programms verwendet wird, dass ausschließlich Standard\-C\+\+\-Syntax verwendet, gelten folgende Richtlinien für die Verwendung der Inlineassembly:  
  
    -   Bei Inlineassemblycode, der von einem bekannten systemeigenen Stapellayout ausgeht und der dazu Konventionen außerhalb der aktuellen Funktion oder andere Informationen über den Computer auf niedriger Ebene abruft, können Fehler auftreten, wenn das Layout für eine verwaltete Funktion auf den Stapelrahmen angewendet wird.  Funktionen, die Inlineassemblycode enthalten, werden als unverwaltete Funktionen generiert, so als wären sie in einem separaten Modul abgelegt, das ohne **\/clr** kompiliert wurde.  
  
    -   Inlineassemblycode wird in Funktionen, die kopierkonstruierte Funktionsparameter übergeben, nicht unterstützt.  
  
-   Die [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md) können nicht aus einem Programm aufgerufen werden, das mit **\/clr** kompiliert wurde.  
  
-   Der [\_\_declspec](../../cpp/declspec.md)\-Modifizierer mit [naked](../../cpp/naked-cpp.md)\-Attribut wird unter \/clr ignoriert.  
  
-   Die **translator**\-Funktion, die durch [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md) eingestellt wird, wirkt sich nur auf abgefangene Elemente im nicht verwalteten Code aus.  Weitere Informationen finden Sie unter [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md).  
  
-   Der Vergleich von Funktionszeigern ist unter **\/clr** nicht zulässig.  
  
-   Der Gebrauch von Funktionen ohne vollständige Prototypen ist unter **\/clr** nicht zulässig.  
  
-   Die folgenden Compileroptionen werden mit **\/clr** nicht unterstützt:  
  
    -   **\/EHsc** und **\/EHs** \(**\/clr** impliziert **\/EHa**, siehe [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md)\)  
  
    -   **\/fp:strict** und **\/fp:except** \(siehe [\/fp \(Festlegen des Gleitkommaverhaltens\)](../../build/reference/fp-specify-floating-point-behavior.md)\)  
  
    -   [\/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)  
  
    -   [\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)  
  
    -   [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)  
  
    -   [\/RTC](../../build/reference/rtc-run-time-error-checks.md)  
  
    -   **\/ZI**  
  
-   Die Kombination aus der `_STATIC_CPPLIB`\-Präprozessordefinition \(`/D_STATIC_CPPLIB`\) und der Compileroption **\/clr** oder **\/clr:pure** wird nicht unterstützt.  Der Grund dafür ist, dass die Definition die Anwendung zu einer Verknüpfung mit der statischen Multithread\-Standard\-C\+\+\-Bibliothek veranlassen würde, was nicht unterstützt wird.  Weitere Informationen finden Sie im Thema [\/MD, \/MT, \/LD \(Laufzeitbibliothek verwenden\)](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
-   [\/J](../../build/reference/j-default-char-type-is-unsigned.md) wird mit **\/clr:safe** oder **\/clr:pure** nicht unterstützt.  
  
-   Die ATL\- und MFC\-Bibliotheken werden von der Kompilierung im pure\-Modus \(**\/clr:pure**\) nicht unterstützt.  Sie können **\/clr:pure** mit der Standard\-C\+\+\-Bibliothek und CRT verwenden, wenn Sie auch mit **\/MD** oder **\/MDd** kompilieren.  
  
-   Die Verwendung von **\/Zi** mit **\/clr** wirkt sich auf die Leistung aus.  Weitere Informationen finden Sie unter [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
-   Das Übergeben eines Breitzeichens an eine .NET Framework\-Ausgaberoutine ohne gleichzeitige Festlegung von [\/Zc:wchar\_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) oder ohne Umwandlung des Zeichens in `__wchar_t` führt zur Darstellung der Ausgabe als `unsigned short int`.  Beispiel:  
  
    ```  
    Console::WriteLine(L' ')              // Will output 32.  
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.  
    ```  
  
-   [\/GS](../../build/reference/gs-buffer-security-check.md) wird beim Kompilieren mit **\/clr** ignoriert, wenn keine Funktion unter `#pragma` [unmanaged](../../preprocessor/managed-unmanaged.md) ist oder die Funktion in systemeigenen Code kompiliert werden muss. In diesem Fall gibt der Compiler die Warnung C4793 aus, die standardmäßig deaktiviert ist.  
  
-   Informationen über die Anforderungen in Bezug auf Funktionssignaturen einer verwalteten Anwendung finden Sie unter [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
-   Mit **\/openmp** und **\/clr** kompilierte Anwendungen können nur in einem einzelnen appdomain\-Prozess ausgeführt werden.  Weitere Informationen finden Sie unter [\/openmp \(Aktivieren der OpenMP 2.0\-Unterstützung\)](../../build/reference/openmp-enable-openmp-2-0-support.md).  
  
-   Funktionen, die eine variable Anzahl von Argumenten \(varargs\) aufnehmen, werden als systemeigene Funktionen generiert.  Alle verwalteten Datentypen in der variablen Argumentposition werden in systemeigene Typen gemarshallt.  Beachten Sie, dass <xref:System.String?displayProperty=fullName>\-Typen in Einzelbyte\-Zeichenfolgen gemarshallt werden, obwohl es sich dabei tatsächlich um breite Zeichenfolgen handelt.  Wenn ein printf\-Spezifizierer also %S \(wchar\_t\*\) lautet, wird er stattdessen in eine %s\-Zeichenfolge gemarshallt.  
  
-   Wenn Sie das Makro va\_arg verwenden, erhalten Sie beim Kompilieren mit **\/clr:pure** möglicherweise unerwartete Ergebnisse.  Weitere Informationen finden Sie unter [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md).  
  
-   Wenn die Anwendung ein Argument vom Typ [va\_list](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) an eine Funktion übergibt, die deklariert wird, um eine [variable Anzahl von Argumenten](../../misc/variable-argument-lists.md) zu akzeptieren, und die Anwendung mit **\/clr:pure** kompiliert wird, löst die CLR <xref:System.NotSupportedException> aus.  Wenn stattdessen **\/clr**  verwendet wird, werden die entsprechenden Funktionen in systemeigenen Code kompiliert und ordnungsgemäß ausgeführt.  Bei Verwendung von **\/clr:safe** wird eine Fehlerdiagnose ausgegeben.  
  
-   Aus verwaltetem Code sollten keine Funktionen aufgerufen werden, die den Stapel durchlaufen, um Parameterinformationen \(Funktionsargumente\) abzurufen. Die P\/Invoke\-Ebene bewirkt, dass Informationen sich weiter unten im Stapel befinden.  Kompilieren Sie z. B. proxy\/stub nicht mit **\/clr**.  
  
-   Funktionen werden nach Möglichkeit zu verwaltetem Code kompiliert, doch nicht alle C\+\+\-Konstrukte können in verwalteten Code übersetzt werden.  Dies wird auf Funktionsbasis ermittelt.  Wenn ein Teil der Funktion nicht in verwalteten Code konvertiert werden kann, wird die gesamte Funktion stattdessen in systemeigenen Code konvertiert.  In den folgenden Fällen wird das Generieren von verwaltetem Code im Compiler verhindert.  
  
    -   Vom Compiler generierte Thunks oder Hilfsfunktionen.  Systemeigene Thunks werden für jeden Funktionsaufruf durch einen Funktionszeiger generiert, einschließlich virtueller Funktionsaufrufe.  
  
    -   Funktionen, die `setjmp` oder `longjmp` aufrufen.  
  
    -   Funktionen, die bestimmte systeminterne Routinen verwenden, um Computerressourcen direkt zu bearbeiten.  Beispielsweise führt die Verwendung von `__enable` und `__disable`, `_ReturnAddress` und `_AddressOfReturnAddress` oder systeminternen Multimediafunktionen zur Erzeugung von systeminternem Code.  
  
    -   Funktionen, die der `#pragma unmanaged`\-Direktive folgen. \(Beachten Sie, dass umgekehrt `#pragma managed` ebenfalls unterstützt wird.\)  
  
    -   Funktionen, die Verweise auf ausgerichtete Typen, d. h. mit `__declspec(align(...))` deklarierte Typen, enthalten.  
  
-   Die [COM\-Unterstützung des Compilers](../../cpp/compiler-com-support.md)\-Klassen können nicht mit **\/clr:pure** oder **\/clr:safe** verwendet werden.  
  
## Siehe auch  
 [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)