---
title: Schreiben eines Ausnahmefilters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 138bb17b8ccbb13371a1c31e4f7347a9bbdbf64b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="writing-an-exception-filter"></a>Schreiben eines Ausnahmefilters
Sie können eine Ausnahme behandeln, indem Sie entweder auf die Ebene des Ausnahmehandlers wechseln oder die Ausführung fortsetzen. Anstatt den Code im Ausnahmehandler, um die Ausnahme und das durchfallen zu behandeln, können Sie *Filter* bereinigen Sie das Problem, und klicken Sie dann durch Zurückgeben von -1, normalen Fluss fortzusetzen, ohne dass der Stapel gelöscht.  
  
> [!NOTE]
>  Einige Ausnahmen können nicht fortgesetzt werden. Wenn *Filter* ergibt auf-1 für eine derartige Ausnahme, löst das System eine neue Ausnahme aus. Beim Aufruf [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), Sie bestimmen, ob die Ausnahme fortgesetzt wird.  
  
 Der folgende Code verwendet beispielsweise einen Funktionsaufruf in der *Filter* Ausdruck: Diese Funktion behandelt das Problem, und klicken Sie dann gibt – 1, um die normalen ablaufsteuerung fortzufahren:  
  
```  
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
  
 Es ist ratsam, verwenden Sie einen Funktionsaufruf in der *Filter* Ausdruck immer *Filter* komplexe Funktionen ausführen muss. Das Auswerten des Ausdrucks verursacht die Ausführung der Funktion, in diesem Fall `Eval_Exception`.  
  
 Beachten Sie die Verwendung von [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) auf die Ausnahme zu bestimmen. Sie müssen diese Funktion innerhalb des Filters selbst aufrufen. `Eval_Exception` kann nicht aufgerufen werden **GetExceptionCode**, muss jedoch den Ausnahmecode übergeben wird.  
  
 Dieser Handler übergibt die Steuerung an einen anderen Handler, sofern die Ausnahme keine Ganzzahl oder ein Gleitkommaüberlauf ist. Wenn dies der Fall ist, ruft der Handler eine Funktion (`ResetVars` ist nur ein Beispiel, keine API-Funktion) auf, um mehrere globale Variablen zurückzusetzen. *Anweisung Anweisungsblock 2*, die in diesem Beispiel leer ist, kann nie ausgeführt werden, da `Eval_Exception` nie exception_execute_handler (1).  
  
 Die Verwendung eines Funktionsaufrufs ist ein gutes allgemeines Verfahren für die Behandlung von komplexen Filterausdrücken. Zwei andere hilfreiche Funktionen der Programmiersprache C sind:  
  
-   Der bedingte Operator  
  
-   Der Kommaoperator  
  
 Der bedingte Operator ist häufig nützlich, da er verwendet werden kann, um nach einem bestimmten Rückgabecode zu suchen und dann einen von zwei unterschiedlichen Werten zurückzugeben. Zum Beispiel erkennt der Filter im folgenden Code die Ausnahme nur, wenn die Ausnahme `STATUS_INTEGER_OVERFLOW` ist:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Der bedingte Operator ist in diesem Fall in erster Linie dafür verantwortlich, Klarheit zu schaffen, da der folgende Code zum gleichen Ergebnis führt:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 Der bedingte Operator ist nützlicher in Situationen, bei dem Sie die Filter-1, EXCEPTION_CONTINUE_EXECUTION auswerten möchten.  
  
 Der Komma-Operator ermöglicht die Ausführung mehrerer unabhängiger Vorgänge innerhalb eines einzelnen Ausdrucks. Die Wirkung gleicht ungefähr der Ausführung mehrerer Anweisungen und der anschließenden Rückgabe des Wertes des letzten Ausdrucks. Der folgenden Code speichert z. B. den Ausnahmecode in einer Variablen und testet dann auf:  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)