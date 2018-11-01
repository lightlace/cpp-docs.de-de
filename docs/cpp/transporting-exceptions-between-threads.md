---
title: Transportieren von Ausnahmen zwischen threads
ms.date: 11/04/2016
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
ms.openlocfilehash: f403b1448855b60f323ed582794a00c3e6ae1b3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464442"
---
# <a name="transporting-exceptions-between-threads"></a>Transportieren von Ausnahmen zwischen threads

Visual C++ unterstützt *Transportieren einer Ausnahme* von einem Thread in einen anderen. Durch das Transportieren von Ausnahmen können Sie eine Ausnahme in einem Thread abfangen und anschließend die Ausnahme scheinbar in einem anderen Thread auslösen lassen. Sie können diese Funktion beispielsweise verwenden, um eine Multithreadanwendung zu schreiben, in der der primäre Thread alle Ausnahmen behandelt, die von seinen sekundären Threads ausgelöst werden. Das Transportieren von Ausnahmen ist insbesondere für Entwickler hilfreich, die parallele Programmierbibliotheken und -systeme erstellen. Um das Transportieren von Ausnahmen zu implementieren, Visual C++ bietet die ["exception_ptr"](../standard-library/exception-typedefs.md#exception_ptr) Typ und die [Current_exception](../standard-library/exception-functions.md#current_exception), [Rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), und [Make_ "exception_ptr"](../standard-library/exception-functions.md#make_exception_ptr) Funktionen.

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
|*nicht angegeben*|Eine nicht angegebene interne Klasse, die verwendet wird, um den Typ `exception_ptr` zu implementieren.|
|*p*|Ein `exception_ptr`-Objekt, das auf eine Ausnahme verweist.|
|*E*|Eine Klasse, die eine Ausnahme darstellt.|
|*e*|Eine Instanz der `E`-Parameterklasse.|

## <a name="return-value"></a>Rückgabewert

Die `current_exception`-Funktion gibt ein `exception_ptr`-Objekt zurück, das auf die Ausnahme verweist, die gerade ausgeführt wird. Wenn keine Ausnahme ausgeführt wird, gibt die Funktion ein `exception_ptr`-Objekt zurück, das keiner Ausnahme zugeordnet ist.

Die `make_exception_ptr` -Funktion zurückgegeben wird ein `exception_ptr` -Objekt, das die Ausnahme, die anhand des verweist auf die *e* Parameter.

## <a name="remarks"></a>Hinweise

### <a name="scenario"></a>Szenario

Angenommen, Sie möchten eine Anwendung erstellen, die skaliert werden kann, um einen variablen Arbeitsaufwand zu verarbeiten. Um dieses Ziel zu erreichen, entwerfen Sie eine Multithreadanwendung, in der ein primärer Ausgangsthread so viele sekundäre Threads erstellt, wie zum Ausführen des Auftrags benötigt werden. Die sekundären Threads helfen dem primären Thread, Ressourcen zu verwalten, einen Lastausgleich vorzunehmen und den Durchsatz zu verbessern. Durch Verteilen der Arbeit zeigt die Multithreadanwendung eine bessere Leistung als eine Singlethreadanwendung.

Wenn jedoch ein sekundärer Thread eine Ausnahme auslöst, sollte diese vom primären Thread behandelt werden. Dies liegt daran, dass die Anwendung Ausnahmen auf konsistente, einheitliche Art und Weise behandeln sollte, unabhängig von der Anzahl von sekundären Threads.

### <a name="solution"></a>Lösung

Um das vorherige Szenario zu behandeln, unterstützt der C++-Standard das Transportieren einer Ausnahme zwischen Threads. Wenn ein sekundärer Thread eine Ausnahme auslöst, wird diese Ausnahme die *aktuelle Ausnahme*. Entsprechend für die reale Welt, die aktuelle Ausnahme gilt als *in-Flight*. Die aktuelle Ausnahme ist aktiv, sobald sie ausgelöst wird, bis der Ausnahmehandler, der sie abfängt, zurückgegeben wird.

Der zweite Thread kann die aktuelle Ausnahme in catch eine **catch** blockieren, und rufen dann die `current_exception` Funktion, die die Ausnahme in speichern eine `exception_ptr` Objekt. Das `exception_ptr`-Objekt muss für den sekundären Thread und den primären Thread verfügbar sein. Beispielsweise kann das `exception_ptr`-Objekt eine globale Variable sein, deren Zugriff durch einen Mutex gesteuert wird. Der Begriff *transport eine Ausnahme* bedeutet, dass eine Ausnahme in einem Thread konvertiert werden kann, um ein Formular, das von einem anderen Thread zugegriffen werden kann.

Anschließend ruft der primäre Thread die `rethrow_exception`-Funktion auf, die die Ausnahme extrahiert und anschließend aus dem `exception_ptr`-Objekt auslöst. Wenn die Ausnahme ausgelöst wird, wird sie zur aktuellen Ausnahme im primären Thread. Das heißt, die Ausnahme stammt scheinbar aus dem primären Thread.

Abschließend kann der primäre Thread die aktuelle Ausnahme in Abfangen einer **catch** blockieren und verarbeiten kann, oder es zu einem Ausnahmehandler höheren Ebene auslösen. Oder der primäre Thread kann die Ausnahme ignorieren und das Beenden des Vorgangs erlauben.

Die meisten Anwendungen müssen keine Ausnahmen zwischen Threads transportieren. Allerdings ist diese Funktion auf einem parallelen Computersystem nützlich, da das System die Arbeit auf sekundäre Threads, Prozessoren oder Kerne aufteilen kann. In einer parallelen Computerumgebung kann ein einzelner, dedizierter Thread alle Ausnahmen von den sekundären Threads behandeln und ein konsistentes Ausnahmebehandlungsmodell für jede Anwendung bieten.

Weitere Informationen zum Antrag des Ausschusses für C++-Standards finden Sie im Internet. Suchen Sie nach der Dokumentnummer N2179 und Sprachenunterstützung für das Transportieren von Ausnahmen zwischen Threads.

### <a name="exception-handling-models-and-compiler-options"></a>Ausnahmebehandlungsmodelle und Compileroptionen

Das Ausnahmebehandlungsmodell Ihrer Anwendung bestimmt, ob eine Ausnahme abgefangen und transportiert werden kann. Visual C++ unterstützt drei Modelle, die C++-Ausnahmen, SEH-Ausnahmen (Structured Exception Handling, Strukturierte Ausnahmebehandlung) und Common Language Runtime (CLR)-Ausnahmen behandeln können. Verwenden der [/EH](../build/reference/eh-exception-handling-model.md) und ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) Compileroptionen Ausnahmebehandlungsmodell Ihrer Anwendung an.

Nur die folgende Kombination von Compileroptionen und Programmieranweisungen kann eine Ausnahme transportieren. Andere Kombinationen können entweder keine Ausnahmen abfangen oder Ausnahmen zwar abfangen, jedoch nicht transportieren.

- Die **/EHa** Compileroption und das **catch** -Anweisung können SEH- und C++-Ausnahmen transportieren.

- Die **/EHa**, **/EHs**, und **/EHsc** Compileroptionen und die **catch** -Anweisung können C++-Ausnahmen transportieren.

- Die **"/ CLR"** Compileroption und das **catch** -Anweisung können C++-Ausnahmen transportieren. Die **"/ CLR"** Compileroption impliziert Spezifikation der **/EHa** Option. Beachten Sie, dass der Compiler das Transportieren von verwalteten Ausnahmen nicht unterstützt. Dies ist, da es sich bei verwalteten Ausnahmen, die abgeleitet sind die [System.Exception-Klasse](../standard-library/exception-class.md), sind bereits Objekte, die Sie zwischen Threads mithilfe der Funktionen der common Language Runtime verschieben können.

   > [!IMPORTANT]
   > Es wird empfohlen, die Sie angeben, die **/EHsc** Compileroption und das nur C++-Ausnahmen abzufangen. Sie verfügbar machen sich auf ein Sicherheitsrisiko bei Verwendung der **/EHa** oder **"/ CLR"** Compileroption und ein **catch** -Anweisung mit einem Auslassungszeichen  *Exception-Deklaration* (`catch(...)`). Sie möchten wahrscheinlich verwenden Sie die **catch** Anweisung, um mehrere spezifische Ausnahmen zu erfassen. Allerdings fängt die `catch(...)`-Anweisung alle C++- und SEH-Ausnahmen ab, einschließlich der unerwarteten Ausnahmen mit schwerwiegenden Ausnahmefehlern. Wenn Sie eine unerwartete Ausnahme nicht korrekt behandeln oder ignorieren, kann Malware-Code diese Möglichkeit nutzen, die Sicherheit Ihres Programms zu beeinträchtigen.

## <a name="usage"></a>Verwendung

In den folgenden Abschnitten wird beschrieben, wie zum Transportieren von Ausnahmen mithilfe der `exception_ptr` Typ und die `current_exception`, `rethrow_exception`, und `make_exception_ptr` Funktionen.

## <a name="exceptionptr-type"></a>exception_ptr-Typ

Verwenden Sie ein `exception_ptr`-Objekt, um auf die aktuelle Ausnahme oder eine Instanz einer vom Benutzer angegebenen Ausnahme zu verweisen. In der Microsoft-Implementierung wird eine Ausnahme von einer [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record)-Struktur dargestellt. Jedes `exception_ptr`-Objekt enthält ein Ausnahmeverweisfeld, das auf eine Kopie der `EXCEPTION_RECORD`-Struktur zeigt, die die Ausnahme darstellt.

Wenn Sie eine `exception_ptr`-Variable deklarieren, wird die Variable keiner Ausnahme zugeordnet. Das heißt, das Ausnahmeverweisfeld ist NULL. Ein solches `exception_ptr`-Objekt wird als *null exception_ptr* bezeichnet.

Verwenden Sie die Funktion `current_exception` oder `make_exception_ptr`, um eine Ausnahme einem `exception_ptr`-Objekt zuzuweisen. Wenn Sie einer `exception_ptr`-Variable eine Ausnahme zuweisen, zeigt das Ausnahmeverweisfeld der Variable auf eine Kopie der Ausnahme. Ist nicht genügend Arbeitsspeicher zum Kopieren der Ausnahme vorhanden, zeigt das Ausnahmeverweisfeld auf eine Kopie einer [std::bad_alloc](../standard-library/bad-alloc-class.md)-Ausnahme. Wenn die `current_exception` oder `make_exception_ptr` Funktion die Ausnahme keinem anderen Grund, die Aufrufe der Funktionen Kopieren der [beenden](../c-runtime-library/reference/terminate-crt.md) Funktion, um den aktuellen Prozess zu beenden.

Trotz seines Namens ist ein `exception_ptr`-Objekt nicht selbst ein Zeiger. Es ist keiner zeigersemantik und kann nicht verwendet werden, mit dem Zeigermemberzugriff (`->`) oder Dereferenzierung (`*`) Operatoren. Das `exception_ptr`-Objekt weist keine öffentlichen Datenmember oder Memberfunktionen auf.

### <a name="comparisons"></a>Vergleiche

Sie können den Gleichheitsoperator (`==`) und den Ungleichheitsoperator (`!=`) verwenden, um zwei `exception_ptr`-Objekte zu vergleichen. Die Operatoren vergleichen nicht den Binärwert (Bitmuster) der `EXCEPTION_RECORD`-Strukturen, die die Ausnahmen darstellen. Stattdessen vergleichen die Operatoren die Adressen im Ausnahmeverweisfeld der `exception_ptr`-Objekte. Folglich sind ein NULL-`exception_ptr` und der NULL-Wert gleichwertig.

## <a name="currentexception-function"></a>current_exception-Funktion

Rufen Sie die `current_exception` -Funktion in einer **catch** Block. Wenn eine Ausnahme aktiv ist und die **catch** Block kann die Ausnahme abfangen, die `current_exception` -Funktion zurückgegeben wird ein `exception_ptr` Objekt, das die Ausnahme verweist. Andernfalls gibt die Funktion ein NULL-`exception_ptr`-Objekt zurück.

### <a name="details"></a>Details

Die `current_exception` -Funktion erfasst die Ausnahme, die aktiv ist, unabhängig davon, ob die **catch** -Anweisung gibt ein [Ausnahmedeklaration](../cpp/try-throw-and-catch-statements-cpp.md) Anweisung.

Der Destruktor für die aktuelle Ausnahme aufgerufen wird, am Ende der **catch** blockieren, wenn Sie die Ausnahme erneut ausgelöst werden. Auch wenn Sie die `current_exception`-Funktion im Destruktor aufrufen, gibt die Funktion ein `exception_ptr`-Objekt zurück, das auf die aktuelle Ausnahme verweist.

Aufeinander folgende Aufrufe der `current_exception`-Funktion geben `exception_ptr`-Objekte zurück, die sich auf unterschiedliche Kopien der aktuellen Ausnahme beziehen. Folglich sind die Objekte bei einem Vergleich ungleich, da sie auf unterschiedliche Kopien verweisen, auch wenn die Kopien den gleichen Binärwert aufweisen.

### <a name="seh-exceptions"></a>SEH-Ausnahmen

Bei Verwendung der **/EHa** -Compileroption verwenden, können Sie eine SEH-Ausnahme abfangen, in einem C++ **catch** Block. Die `current_exception`-Funktion gibt ein `exception_ptr`-Objekt zurück, das auf die SEH-Ausnahme verweist. Und die `rethrow_exception` -Funktion löst die SEH-Ausnahme aus, wenn Sie es mit Thetransported Aufrufen `exception_ptr` Objekt als Argument.

Die `current_exception` Funktionsergebnis ist ein NULL-Wert `exception_ptr` Aufruf in eine SEH- **__finally** Beendigungshandler, ein **__except** Ausnahmehandler oder **__except**Filterausdruck.

Eine transportierte Ausnahme unterstützt keine geschachtelte Ausnahmen. Eine geschachtelte Ausnahme tritt auf, wenn eine andere Ausnahme ausgelöst wird, während eine Ausnahme behandelt wird. Wenn Sie eine geschachtelte Ausnahme abfangen, zeigt der `EXCEPTION_RECORD.ExceptionRecord`-Datenmember auf eine Kette von `EXCEPTION_RECORD`-Strukturen, die die zugeordneten Ausnahmen beschreiben. Die `current_exception`-Funktion unterstützt keine geschachtelte Ausnahmen, da sie ein `exception_ptr`-Objekt zurückgibt, dessen `ExceptionRecord`-Datenmember auf Null gesetzt ist.

Wenn Sie eine SEH-Ausnahme abfangen, müssen Sie den Speicher verwalten, auf den von einem Zeiger im `EXCEPTION_RECORD.ExceptionInformation`-Datenmemberarray verwiesen wird. Sie müssen sicherstellen, dass der Arbeitsspeicher während der Lebensdauer des entsprechenden `exception_ptr`-Objekts gültig ist und dass der Arbeitsspeicher freigegeben wird, wenn das `exception_ptr`-Objekt gelöscht wird.

Sie können Funktionen des Konvertierungsprogramms für strukturierte Ausnahmen zusammen mit der Funktion für den Ausnahmetransport verwenden. Wenn eine SEH-Ausnahme in eine C++-Ausnahme übersetzt wird, gibt die `current_exception`-Funktion einen `exception_ptr` zurück, der auf die übersetzte Ausnahme anstelle der ursprünglichen SEH-Ausnahme verweist. Die `rethrow_exception`-Funktion löst daraufhin die übersetzte Ausnahme, nicht die ursprüngliche Ausnahme, aus. Weitere Informationen zu SE übersetzerfunktionen, finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrowexception-function"></a>rethrow_exception-Funktion

Nachdem Sie eine abgefangene Ausnahme in einem `exception_ptr`-Objekt gespeichert haben, kann der primäre Thread das Objekt verarbeiten. Rufen Sie in Ihrem primären Thread die `rethrow_exception`-Funktion zusammen mit dem `exception_ptr`-Objekt als Argument auf. Die `rethrow_exception`-Funktion extrahiert die Ausnahme vom `exception_ptr`-Objekt und löst die Ausnahme anschließend im Kontext des primären Threads aus. Wenn die *p* Parameter, der die `rethrow_exception` -Funktion ist ein NULL-Wert `exception_ptr`, löst die Funktion [Std:: bad_exception](../standard-library/bad-exception-class.md).

Die extrahierte Ausnahme ist jetzt die aktuelle Ausnahme im primären Thread, und Sie können sie behandeln wie jede andere Ausnahme. Wenn Sie die Ausnahme abfangen, Sie können sie sofort verarbeiten oder eine **auslösen** Anweisung an einen Ausnahmehandler höherer Ebene zu senden. Unternehmen Sie anderenfalls nichts, und lassen Sie den standardmäßigen Systemausnahmehandler den Prozess beenden.

## <a name="makeexceptionptr-function"></a>make_exception_ptr-Funktion

Die `make_exception_ptr`-Funktion akzeptiert eine Instanz einer Klasse als Argument und gibt dann einen `exception_ptr` zurück, der auf die Instanz verweist. Normalerweise geben Sie ein [exception class](../standard-library/exception-class.md)-Objekt als Argument für die `make_exception_ptr`-Funktion an, obwohl jedes Klassenobjekt als Argument zulässig ist.

Aufrufen der `make_exception_ptr` Funktion ist gleichbedeutend mit dem Auslösen einer C++-Ausnahme abfangen in einer **catch** Block, und dem anschließenden Aufrufen der `current_exception` Funktion zurückgibt ein `exception_ptr` Objekt, das die Ausnahme verweist. Die Microsoft-Implementierung der `make_exception_ptr`-Funktion ist effizienter als das Auslösen und anschließende Abfangen einer Ausnahme.

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