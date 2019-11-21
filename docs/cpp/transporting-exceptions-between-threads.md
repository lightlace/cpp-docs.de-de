---
title: Transportieren von Ausnahmen zwischen Threads
ms.date: 05/07/2019
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
ms.openlocfilehash: 25b09c508b932a4d1470f6b23f03aa52e62c68cc
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246313"
---
# <a name="transporting-exceptions-between-threads"></a>Transportieren von Ausnahmen zwischen Threads

The Microsoft C++ compiler (MSVC) supports *transporting an exception* from one thread to another. Durch das Transportieren von Ausnahmen können Sie eine Ausnahme in einem Thread abfangen und anschließend die Ausnahme scheinbar in einem anderen Thread auslösen lassen. Sie können diese Funktion beispielsweise verwenden, um eine Multithreadanwendung zu schreiben, in der der primäre Thread alle Ausnahmen behandelt, die von seinen sekundären Threads ausgelöst werden. Das Transportieren von Ausnahmen ist insbesondere für Entwickler hilfreich, die parallele Programmierbibliotheken und -systeme erstellen. To implement transporting exceptions, MSVC provides the [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) type and the [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), and [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) functions.

## <a name="syntax"></a>Syntax

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*unspecified*|Eine nicht angegebene interne Klasse, die verwendet wird, um den Typ `exception_ptr` zu implementieren.|
|*p*|Ein `exception_ptr`-Objekt, das auf eine Ausnahme verweist.|
|*E*|Eine Klasse, die eine Ausnahme darstellt.|
|*e*|Eine Instanz der `E`-Parameterklasse.|

## <a name="return-value"></a>Rückgabewert

Die `current_exception`-Funktion gibt ein `exception_ptr`-Objekt zurück, das auf die Ausnahme verweist, die gerade ausgeführt wird. Wenn keine Ausnahme ausgeführt wird, gibt die Funktion ein `exception_ptr`-Objekt zurück, das keiner Ausnahme zugeordnet ist.

The `make_exception_ptr` function returns an `exception_ptr` object that references the exception specified by the *e* parameter.

## <a name="remarks"></a>Hinweise

### <a name="scenario"></a>Szenario

Angenommen, Sie möchten eine Anwendung erstellen, die skaliert werden kann, um einen variablen Arbeitsaufwand zu verarbeiten. Um dieses Ziel zu erreichen, entwerfen Sie eine Multithreadanwendung, in der ein primärer Ausgangsthread so viele sekundäre Threads erstellt, wie zum Ausführen des Auftrags benötigt werden. Die sekundären Threads helfen dem primären Thread, Ressourcen zu verwalten, einen Lastausgleich vorzunehmen und den Durchsatz zu verbessern. Durch Verteilen der Arbeit zeigt die Multithreadanwendung eine bessere Leistung als eine Singlethreadanwendung.

Wenn jedoch ein sekundärer Thread eine Ausnahme auslöst, sollte diese vom primären Thread behandelt werden. Dies liegt daran, dass die Anwendung Ausnahmen auf konsistente, einheitliche Art und Weise behandeln sollte, unabhängig von der Anzahl von sekundären Threads.

### <a name="solution"></a>Lösung

Um das vorherige Szenario zu behandeln, unterstützt der C++-Standard das Transportieren einer Ausnahme zwischen Threads. If a secondary thread throws an exception, that exception becomes the *current exception*. By analogy to the real world, the current exception is said to be *in flight*. Die aktuelle Ausnahme ist aktiv, sobald sie ausgelöst wird, bis der Ausnahmehandler, der sie abfängt, zurückgegeben wird.

The secondary thread can catch the current exception in a **catch** block, and then call the `current_exception` function to store the exception in an `exception_ptr` object. Das `exception_ptr`-Objekt muss für den sekundären Thread und den primären Thread verfügbar sein. Beispielsweise kann das `exception_ptr`-Objekt eine globale Variable sein, deren Zugriff durch einen Mutex gesteuert wird. The term *transport an exception* means an exception in one thread can be converted to a form that can be accessed by another thread.

Anschließend ruft der primäre Thread die `rethrow_exception`-Funktion auf, die die Ausnahme extrahiert und anschließend aus dem `exception_ptr`-Objekt auslöst. Wenn die Ausnahme ausgelöst wird, wird sie zur aktuellen Ausnahme im primären Thread. Das heißt, die Ausnahme stammt scheinbar aus dem primären Thread.

Finally, the primary thread can catch the current exception in a **catch** block and then process it or throw it to a higher level exception handler. Oder der primäre Thread kann die Ausnahme ignorieren und das Beenden des Vorgangs erlauben.

Die meisten Anwendungen müssen keine Ausnahmen zwischen Threads transportieren. Allerdings ist diese Funktion auf einem parallelen Computersystem nützlich, da das System die Arbeit auf sekundäre Threads, Prozessoren oder Kerne aufteilen kann. In einer parallelen Computerumgebung kann ein einzelner, dedizierter Thread alle Ausnahmen von den sekundären Threads behandeln und ein konsistentes Ausnahmebehandlungsmodell für jede Anwendung bieten.

Weitere Informationen zum Antrag des Ausschusses für C++-Standards finden Sie im Internet. Suchen Sie nach der Dokumentnummer N2179 und Sprachenunterstützung für das Transportieren von Ausnahmen zwischen Threads.

### <a name="exception-handling-models-and-compiler-options"></a>Exception-handling models and compiler options

Das Ausnahmebehandlungsmodell Ihrer Anwendung bestimmt, ob eine Ausnahme abgefangen und transportiert werden kann. Visual C++ unterstützt drei Modelle, die C++-Ausnahmen, SEH-Ausnahmen (Structured Exception Handling, Strukturierte Ausnahmebehandlung) und Common Language Runtime (CLR)-Ausnahmen behandeln können. Use the [/EH](../build/reference/eh-exception-handling-model.md) and [/clr](../build/reference/clr-common-language-runtime-compilation.md) compiler options to specify your application's exception-handling model.

Nur die folgende Kombination von Compileroptionen und Programmieranweisungen kann eine Ausnahme transportieren. Andere Kombinationen können entweder keine Ausnahmen abfangen oder Ausnahmen zwar abfangen, jedoch nicht transportieren.

- The **/EHa** compiler option and the **catch** statement can transport SEH and C++ exceptions.

- The **/EHa**, **/EHs**, and **/EHsc** compiler options and the **catch** statement can transport C++ exceptions.

- The **/CLR** compiler option and the **catch** statement can transport C++ exceptions. The **/CLR** compiler option implies specification of the **/EHa** option. Beachten Sie, dass der Compiler das Transportieren von verwalteten Ausnahmen nicht unterstützt. This is because managed exceptions, which are derived from the [System.Exception class](../standard-library/exception-class.md), are already objects that you can move between threads by using the facilities of the common languange runtime.

   > [!IMPORTANT]
   > We recommend that you specify the **/EHsc** compiler option and catch only C++ exceptions. You expose yourself to a security threat if you use the **/EHa** or **/CLR** compiler option and a **catch** statement with an ellipsis *exception-declaration* (`catch(...)`). You probably intend to use the **catch** statement to capture a few specific exceptions. Allerdings fängt die `catch(...)`-Anweisung alle C++- und SEH-Ausnahmen ab, einschließlich der unerwarteten Ausnahmen mit schwerwiegenden Ausnahmefehlern. Wenn Sie eine unerwartete Ausnahme nicht korrekt behandeln oder ignorieren, kann Malware-Code diese Möglichkeit nutzen, die Sicherheit Ihres Programms zu beeinträchtigen.

## <a name="usage"></a>Verwendung

The following sections describe how to transport exceptions by using the `exception_ptr` type, and the `current_exception`, `rethrow_exception`, and `make_exception_ptr` functions.

## <a name="exception_ptr-type"></a>exception_ptr type

Verwenden Sie ein `exception_ptr`-Objekt, um auf die aktuelle Ausnahme oder eine Instanz einer vom Benutzer angegebenen Ausnahme zu verweisen. In der Microsoft-Implementierung wird eine Ausnahme von einer [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record)-Struktur dargestellt. Jedes `exception_ptr`-Objekt enthält ein Ausnahmeverweisfeld, das auf eine Kopie der `EXCEPTION_RECORD`-Struktur zeigt, die die Ausnahme darstellt.

Wenn Sie eine `exception_ptr`-Variable deklarieren, wird die Variable keiner Ausnahme zugeordnet. Das heißt, das Ausnahmeverweisfeld ist NULL. Ein solches `exception_ptr`-Objekt wird als *null exception_ptr* bezeichnet.

Verwenden Sie die Funktion `current_exception` oder `make_exception_ptr`, um eine Ausnahme einem `exception_ptr`-Objekt zuzuweisen. Wenn Sie einer `exception_ptr`-Variable eine Ausnahme zuweisen, zeigt das Ausnahmeverweisfeld der Variable auf eine Kopie der Ausnahme. Ist nicht genügend Arbeitsspeicher zum Kopieren der Ausnahme vorhanden, zeigt das Ausnahmeverweisfeld auf eine Kopie einer [std::bad_alloc](../standard-library/bad-alloc-class.md)-Ausnahme. If the `current_exception` or `make_exception_ptr` function cannot copy the exception for any other reason, the function calls the [terminate](../c-runtime-library/reference/terminate-crt.md) function to exit the current process.

Trotz seines Namens ist ein `exception_ptr`-Objekt nicht selbst ein Zeiger. It does not obey pointer semantics and cannot be used with the pointer member access (`->`) or indirection (`*`) operators. Das `exception_ptr`-Objekt weist keine öffentlichen Datenmember oder Memberfunktionen auf.

### <a name="comparisons"></a>Vergleiche

Sie können den Gleichheitsoperator (`==`) und den Ungleichheitsoperator (`!=`) verwenden, um zwei `exception_ptr`-Objekte zu vergleichen. Die Operatoren vergleichen nicht den Binärwert (Bitmuster) der `EXCEPTION_RECORD`-Strukturen, die die Ausnahmen darstellen. Stattdessen vergleichen die Operatoren die Adressen im Ausnahmeverweisfeld der `exception_ptr`-Objekte. Folglich sind ein NULL-`exception_ptr` und der NULL-Wert gleichwertig.

## <a name="current_exception-function"></a>current_exception function

Call the `current_exception` function in a **catch** block. If an exception is in flight and the **catch** block can catch the exception, the `current_exception` function returns an `exception_ptr` object that references the exception. Andernfalls gibt die Funktion ein NULL-`exception_ptr`-Objekt zurück.

### <a name="details"></a>Details

The `current_exception` function captures the exception that is in flight regardless of whether the **catch** statement specifies an [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md) statement.

The destructor for the current exception is called at the end of the **catch** block if you do not rethrow the exception. Auch wenn Sie die `current_exception`-Funktion im Destruktor aufrufen, gibt die Funktion ein `exception_ptr`-Objekt zurück, das auf die aktuelle Ausnahme verweist.

Aufeinander folgende Aufrufe der `current_exception`-Funktion geben `exception_ptr`-Objekte zurück, die sich auf unterschiedliche Kopien der aktuellen Ausnahme beziehen. Folglich sind die Objekte bei einem Vergleich ungleich, da sie auf unterschiedliche Kopien verweisen, auch wenn die Kopien den gleichen Binärwert aufweisen.

### <a name="seh-exceptions"></a>SEH exceptions

If you use the **/EHa** compiler option, you can catch an SEH exception in a C++ **catch** block. Die `current_exception`-Funktion gibt ein `exception_ptr`-Objekt zurück, das auf die SEH-Ausnahme verweist. And the `rethrow_exception` function throws the SEH exception if you call it with thetransported `exception_ptr` object as its argument.

The `current_exception` function returns a null `exception_ptr` if you call it in an SEH **__finally** termination handler, an **__except** exception handler, or the **__except** filter expression.

Eine transportierte Ausnahme unterstützt keine geschachtelte Ausnahmen. Eine geschachtelte Ausnahme tritt auf, wenn eine andere Ausnahme ausgelöst wird, während eine Ausnahme behandelt wird. Wenn Sie eine geschachtelte Ausnahme abfangen, zeigt der `EXCEPTION_RECORD.ExceptionRecord`-Datenmember auf eine Kette von `EXCEPTION_RECORD`-Strukturen, die die zugeordneten Ausnahmen beschreiben. Die `current_exception`-Funktion unterstützt keine geschachtelte Ausnahmen, da sie ein `exception_ptr`-Objekt zurückgibt, dessen `ExceptionRecord`-Datenmember auf Null gesetzt ist.

Wenn Sie eine SEH-Ausnahme abfangen, müssen Sie den Speicher verwalten, auf den von einem Zeiger im `EXCEPTION_RECORD.ExceptionInformation`-Datenmemberarray verwiesen wird. Sie müssen sicherstellen, dass der Arbeitsspeicher während der Lebensdauer des entsprechenden `exception_ptr`-Objekts gültig ist und dass der Arbeitsspeicher freigegeben wird, wenn das `exception_ptr`-Objekt gelöscht wird.

Sie können Funktionen des Konvertierungsprogramms für strukturierte Ausnahmen zusammen mit der Funktion für den Ausnahmetransport verwenden. Wenn eine SEH-Ausnahme in eine C++-Ausnahme übersetzt wird, gibt die `current_exception`-Funktion einen `exception_ptr` zurück, der auf die übersetzte Ausnahme anstelle der ursprünglichen SEH-Ausnahme verweist. Die `rethrow_exception`-Funktion löst daraufhin die übersetzte Ausnahme, nicht die ursprüngliche Ausnahme, aus. For more information about SE translator functions, see [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception function

Nachdem Sie eine abgefangene Ausnahme in einem `exception_ptr`-Objekt gespeichert haben, kann der primäre Thread das Objekt verarbeiten. Rufen Sie in Ihrem primären Thread die `rethrow_exception`-Funktion zusammen mit dem `exception_ptr`-Objekt als Argument auf. Die `rethrow_exception`-Funktion extrahiert die Ausnahme vom `exception_ptr`-Objekt und löst die Ausnahme anschließend im Kontext des primären Threads aus. If the *p* parameter of the `rethrow_exception` function is a null `exception_ptr`, the function throws [std::bad_exception](../standard-library/bad-exception-class.md).

Die extrahierte Ausnahme ist jetzt die aktuelle Ausnahme im primären Thread, und Sie können sie behandeln wie jede andere Ausnahme. If you catch the exception, you can handle it immediately or use a **throw** statement to send it to a higher level exception handler. Unternehmen Sie anderenfalls nichts, und lassen Sie den standardmäßigen Systemausnahmehandler den Prozess beenden.

## <a name="make_exception_ptr-function"></a>make_exception_ptr-Funktion

Die `make_exception_ptr`-Funktion akzeptiert eine Instanz einer Klasse als Argument und gibt dann einen `exception_ptr` zurück, der auf die Instanz verweist. Normalerweise geben Sie ein [exception class](../standard-library/exception-class.md)-Objekt als Argument für die `make_exception_ptr`-Funktion an, obwohl jedes Klassenobjekt als Argument zulässig ist.

Calling the `make_exception_ptr` function is equivalent to throwing a C++ exception, catching it in a **catch** block, and then calling the `current_exception` function to return an `exception_ptr` object that references the exception. Die Microsoft-Implementierung der `make_exception_ptr`-Funktion ist effizienter als das Auslösen und anschließende Abfangen einer Ausnahme.

Eine Anwendung erfordert in der Regel nicht die `make_exception_ptr` -Funktion, und es wird von ihrer Verwendung abgeraten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Standard-C++-Ausnahme und eine benutzerdefinierte C++-Ausnahme von einem Thread zu einem anderen transportiert.

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md)
