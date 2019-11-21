---
title: Schreiben eines Ausnahmefilters
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: aaf0dc77207399d7c6be86127d7decf03895ced5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245983"
---
# <a name="writing-an-exception-filter"></a>Schreiben eines Ausnahmefilters

Sie können eine Ausnahme behandeln, indem Sie entweder auf die Ebene des Ausnahmehandlers wechseln oder die Ausführung fortsetzen. Instead of using the exception handler code to handle the exception and falling through, you can use *filter* to clean up the problem and then, by returning -1, resume normal flow without clearing the stack.

> [!NOTE]
>  Einige Ausnahmen können nicht fortgesetzt werden. If *filter* evaluates to -1 for such an exception, the system raises a new exception. When you call [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception), you determine whether the exception will continue.

For example, the following code uses a function call in the *filter* expression: this function handles the problem and then returns -1 to resume normal flow of control:

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

It is a good idea to use a function call in the *filter* expression whenever *filter* needs to do anything complex. Das Auswerten des Ausdrucks verursacht die Ausführung der Funktion, in diesem Fall `Eval_Exception`.

Note the use of [GetExceptionCode](/windows/win32/Debug/getexceptioncode) to determine the exception. Sie müssen diese Funktion innerhalb des Filters selbst aufrufen. `Eval_Exception` cannot call `GetExceptionCode`, but it must have the exception code passed to it.

Dieser Handler übergibt die Steuerung an einen anderen Handler, sofern die Ausnahme keine Ganzzahl oder ein Gleitkommaüberlauf ist. Wenn dies der Fall ist, ruft der Handler eine Funktion (`ResetVars` ist nur ein Beispiel, keine API-Funktion) auf, um mehrere globale Variablen zurückzusetzen. *Statement-block-2*, which in this example is empty, can never be executed because `Eval_Exception` never returns EXCEPTION_EXECUTE_HANDLER (1).

Die Verwendung eines Funktionsaufrufs ist ein gutes allgemeines Verfahren für die Behandlung von komplexen Filterausdrücken. Zwei andere hilfreiche Funktionen der Programmiersprache C sind:

- Der bedingte Operator

- Der Kommaoperator

Der bedingte Operator ist häufig nützlich, da er verwendet werden kann, um nach einem bestimmten Rückgabecode zu suchen und dann einen von zwei unterschiedlichen Werten zurückzugeben. For example, the filter in the following code recognizes the exception only if the exception is STATUS_INTEGER_OVERFLOW:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Der bedingte Operator ist in diesem Fall in erster Linie dafür verantwortlich, Klarheit zu schaffen, da der folgende Code zum gleichen Ergebnis führt:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

The conditional operator is more useful in situations where you might want the filter to evaluate to -1, EXCEPTION_CONTINUE_EXECUTION.

Der Komma-Operator ermöglicht die Ausführung mehrerer unabhängiger Vorgänge innerhalb eines einzelnen Ausdrucks. Die Wirkung gleicht ungefähr der Ausführung mehrerer Anweisungen und der anschließenden Rückgabe des Wertes des letzten Ausdrucks. Der folgenden Code speichert z. B. den Ausnahmecode in einer Variablen und testet dann auf:

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>Siehe auch

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)