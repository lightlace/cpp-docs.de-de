---
title: "Schreiben eines Ausnahmefilters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Filter"
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Schreiben eines Ausnahmefilters
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine Ausnahme behandeln, indem Sie entweder auf die Ebene des Ausnahmehandlers wechseln oder die Ausführung fortsetzen.  Statt den Code im Ausnahmehandler zu verwenden, um die Ausnahme und das Durchfallen zu behandeln, können Sie *filter* verwenden, um das Problem zu bereinigen und anschließend, durch die Rückgabe von –1, den normalen Fluss fortzusetzen, ohne den Stapel zu löschen.  
  
> [!NOTE]
>  Einige Ausnahmen können nicht fortgesetzt werden.  Wenn *filter* für eine derartige Ausnahme –1 ergibt, löst das System eine neue Ausnahme aus.  Wenn Sie [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) aufrufen, bestimmen Sie, ob die Ausnahme fortgesetzt wird.  
  
 Beispielsweise verwendet der folgende Code einen Funktionsaufruf im *filter*\-Ausdruck: Diese Funktion behandelt das Problem und gibt \-1 zurück, um mit der normalen Ablaufsteuerung fortzufahren:  
  
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
  
 Sie sollten einen Funktionsaufruf im *filter*\-Ausdruck verwenden, sobald *filter* komplexe Funktionen ausführen muss.  Das Auswerten des Ausdrucks verursacht die Ausführung der Funktion, in diesem Fall `Eval_Exception`.  
  
 Beachten Sie die Verwendung von [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356), um die Ausnahme zu bestimmen.  Sie müssen diese Funktion innerhalb des Filters selbst aufrufen.  `Eval_Exception` kann **GetExceptionCode** nicht aufrufen, jedoch muss ihr der Ausnahmecode übergeben werden.  
  
 Dieser Handler übergibt die Steuerung an einen anderen Handler, sofern die Ausnahme keine Ganzzahl oder ein Gleitkommaüberlauf ist.  Wenn dies der Fall ist, ruft der Handler eine Funktion \(`ResetVars` ist nur ein Beispiel, keine API\-Funktion\) auf, um mehrere globale Variablen zurückzusetzen.  *Anweisungsblock 2*, der in diesem Beispiel leer ist, kann nie ausgeführt werden, da `Eval_Exception` nie EXCEPTION\_EXECUTE\_HANDLER \(1\) zurückgibt.  
  
 Die Verwendung eines Funktionsaufrufs ist ein gutes allgemeines Verfahren für die Behandlung von komplexen Filterausdrücken.  Zwei andere hilfreiche Funktionen der Programmiersprache C sind:  
  
-   Der bedingte Operator  
  
-   Der Kommaoperator  
  
 Der bedingte Operator ist häufig nützlich, da er verwendet werden kann, um nach einem bestimmten Rückgabecode zu suchen und dann einen von zwei unterschiedlichen Werten zurückzugeben.  Zum Beispiel erkennt der Filter im folgenden Code die Ausnahme nur, wenn die Ausnahme `STATUS_INTEGER_OVERFLOW` ist:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Der bedingte Operator ist in diesem Fall in erster Linie dafür verantwortlich, Klarheit zu schaffen, da der folgende Code zum gleichen Ergebnis führt:  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 Der bedingte Operator ist in Situationen, in denen der Filter \-1, EXCEPTION\_CONTINUE\_EXECUTION auswerten soll, nützlicher.  
  
 Der Komma\-Operator ermöglicht die Ausführung mehrerer unabhängiger Vorgänge innerhalb eines einzelnen Ausdrucks.  Die Wirkung gleicht ungefähr der Ausführung mehrerer Anweisungen und der anschließenden Rückgabe des Wertes des letzten Ausdrucks.  Der folgenden Code speichert z. B. den Ausnahmecode in einer Variablen und testet dann auf:  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)