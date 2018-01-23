---
title: Ausnahmespezifikationen (Throw, Noexcept) (C++) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd96f666c4733f1c9b1aff65705840a46729194c
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="exception-specifications-throw-noexcept-c"></a>Ausnahmespezifikationen (Throw, Noexcept) (C++)

Ausnahmespezifikationen sind eine Sprachfunktion in C++, die der Programmierer die Ausnahmetypen angeben, die von einer Funktion weitergegeben werden können. Sie können angeben, dass eine Funktion kann nicht mithilfe von einer Ausnahme beendet ggf. ein *Ausnahmespezifikation*. Der Compiler kann diese Informationen verwenden, um die Aufrufe an die Funktion zu optimieren und versieht die Funktion zum Beenden des Programms, wenn eine unerwartete Ausnahme. 

Vor C ++ 17 gab es zwei Arten von Ausnahmespezifikation. Die *Noexcept-Spezifikation* seit C ++ 11. Es gibt an, ob der Satz der möglichen Ausnahmen, die überwechseln können, dass Sie die Funktion leer ist. Die *dynamische Ausnahmespezifikation*, oder `throw(optional_type_list)` -Spezifikation wurde in C ++ 11 als veraltet markiert und in C ++ 17 entfernt wird, mit Ausnahme von `throw()`, also ein Alias für `noexcept(true)`. Diese Ausnahmespezifikation wurde entworfen, um zusammenfassende Informationen dazu, welche Ausnahmen können, aus einer Funktion ausgelöst werden bereitzustellen, aber in der Praxis befand er sich problematisch sein. Eine dynamische Ausnahmespezifikation, die sich als nützlich erwies wurde die unbedingte `throw()` Spezifikation. Um beispielsweise die Funktionsdeklaration:

```cpp
void MyFunction(int i) throw();
```

 weist den Compiler an, dass die Funktion keine Ausnahmen auslöst. Allerdings in **/std:c ++ 14** Modus könnte dies zu nicht definiertes Verhalten, wenn die Funktion eine Ausnahme auslöst. Daher empfehlen wir verwenden die [Noexcept](../cpp/noexcept-cpp.md) Operator oben:

```cpp
void MyFunction(int i) noexcept;
```

In der folgenden Tabelle wird die Implementierung von Ausnahmespezifikationen in Visual C++ zusammengefasst.

|Ausnahmespezifikation|Bedeutung|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|Die Funktion löst keine Ausnahme aus. In [/std:c ++ 14](../build/reference/std-specify-language-standard-version.md) Modus (Standard), `noexcept` und `noexcept(true)` sind gleichwertig. Wenn eine Ausnahme ausgelöst wird, von einer Funktion, die deklariert wird `noexcept` oder `noexcept(true)`, [Terminate](../standard-library/exception-functions.md#terminate) aufgerufen wird. Wenn eine Ausnahme ausgelöst wird, von einer Funktion deklariert als `throw()` in **/std:c ++ 14** Modus, das Ergebnis ist nicht definiertes Verhalten. Es wird keine bestimmte Funktion aufgerufen. Dies ist eine Abweichung von der C ++ 14-standard, die den Compiler aufzurufenden erforderlich [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br> **Visual Studio 2017 15.5 und höher**: In **/std:c ++ 17** Modus `noexcept`, `noexcept(true)`, und `throw()` alle äquivalent sind. In **/std:c ++ 17** Modus `throw()` ist ein Alias für `noexcept(true)`. In **/std:c ++ 17** Modus, wenn eine Ausnahme, von einer Funktion deklariert, die mit den Spezifikationen ausgelöst wird [Terminate](../standard-library/exception-functions.md#terminate) wird aufgerufen, wie für C ++ 17-standard erforderlich.|
|`noexcept(false)`<br/>`throw(...)`<br/>Keine Angabe|Die Funktion kann eine Ausnahme eines beliebigen Typs.|
|`throw(type)`| (**C ++ 14 und früher**) die Funktion kann eine Ausnahme vom Typ `type`. Microsoft C++-Compiler akzeptiert die Syntax, aber interpretiert ihn als `noexcept(false)`. In **/std:c ++ 17** Modus der Compiler die Warnung C5040.|

 Behandlung von Ausnahmen in einer Anwendung verwendet, es muss eine Funktion in der Aufrufliste, die Handles Ausnahmen ausgelöst, bevor sie den äußeren Bereich einer Funktion beendet markiert `noexcept`, `noexcept(true)`, oder `throw()`. Wenn alle Funktionen zwischen aufgerufen derjenige, der eine Ausnahme auslöst und das Projekt, das die Ausnahme behandelt werden als angegeben `noexcept`, `noexcept(true)` (oder `throw()` in **/std:c ++ 17** Modus), das Programm wird beendet, wenn die Noexcept-Funktion gibt die Ausnahme weiter.

 Das Ausnahmeverhalten einer Funktion hängt von den folgenden Faktoren ab:

- Die [Sprache standard Kompilierungsmodus](../build/reference/std-specify-language-standard-version.md) festgelegt ist.
- Ob die Funktion mit C oder C++ kompiliert wird.

- Die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption verwendet.

- Ob die Ausnahmespezifikation explizit angegeben wird.

 Explizite Ausnahmespezifikationen sind für C-Funktionen nicht zulässig. Eine C-Funktion wird davon ausgegangen, dass nicht Auslösen von Ausnahmen unter **/EHsc /**, und strukturierte Ausnahmen auslösen **/EHs**, **/EHa**, oder **EHac**.

 In der folgenden Tabelle wird zusammengefasst, ob es sich bei eine C++-Funktion möglicherweise unter verschiedenen Optionen der Compiler-Ausnahmebehandlung auslösen kann:

|Funktion|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|C++-Funktion ohne Ausnahmespezifikation|Ja|Ja|Ja|Ja|
|C++-Funktion mit `noexcept`, `noexcept(true)`, oder `throw()` Ausnahmespezifikation|Nein|Nein|Ja|Ja|
|C++-Funktion mit `noexcept(false)`, `throw(...)`, oder `throw(type)` Ausnahmespezifikation|Ja|Ja|Ja|Ja|

## <a name="example"></a>Beispiel

```cpp
// exception_specification.cpp
// compile with: /EHs
#include <stdio.h>

void handler() {
   printf_s("in handler\n");
}

void f1(void) throw(int) {
   printf_s("About to throw 1\n");
   if (1)
      throw 1;
}

void f5(void) throw() {
   try {
      f1();
   }
   catch(...) {
      handler();
    }
}

// invalid, doesn't handle the int exception thrown from f1()
// void f3(void) throw() {
//   f1();
// }

void __declspec(nothrow) f2(void) {
   try {
      f1();
   }
   catch(int) {
      handler();
    }
}

// only valid if compiled without /EHc 
// /EHc means assume extern "C" functions don't throw exceptions
extern "C" void f4(void);
void f4(void) {
   f1();
}

int main() {
   f2();

   try {
      f4();
   }
   catch(...) {
      printf_s("Caught exception from f4\n");
   }
   f5();
}
```

```Output
About to throw 1
in handler
About to throw 1
Caught exception from f4
About to throw 1
in handler
```

## <a name="see-also"></a>Siehe auch

 [Versuchen Sie es, throw- und catch-Anweisungen (C++)](../cpp/try-throw-and-catch-statements-cpp.md) [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)