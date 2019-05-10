---
title: Ausnahmespezifikationen (Throw, "noexcept") (C++)
ms.date: 01/18/2018
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
ms.openlocfilehash: a3d4c0446cd8dde83febb1b4269811b5dec3c477
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222102"
---
# <a name="exception-specifications-throw-noexcept-c"></a>Ausnahmespezifikationen (Throw, "noexcept") (C++)

Ausnahmespezifikationen sind eine Sprachfunktion in C++, die angeben, der Programmierer zu den Ausnahmetypen, die von einer Funktion weitergegeben werden können. Sie können angeben, dass eine Funktion kann oder nicht durch eine Ausnahme, mithilfe beenden kann einer *Ausnahmespezifikation*. Der Compiler kann diese Informationen verwenden, um Aufrufe an die Funktion zu optimieren, und schützt die Funktion zum Beenden des Programms, wenn eine unerwartete Ausnahme.

Vor C ++ 17 gab es zwei Arten von Ausnahmespezifikation. Die *"noexcept" Spezifikation* ist neu in C ++ 11. Es gibt an, ob der Satz von möglichen Ausnahmen, die die Funktion mit Escapezeichen versehen können leer ist. Die *dynamischen Ausnahmespezifikation*, oder `throw(optional_type_list)` -Spezifikation wurde in C ++ 11 als veraltet markiert und in C ++ 17 entfernt werden, mit Ausnahme von `throw()`, d.h. ein Alias für `noexcept(true)`. Diese Ausnahmespezifikation wurde entworfen, um zusammenfassende Informationen dazu, welche Ausnahmen können, aus einer Funktion ausgelöst werden bereitzustellen, aber in der Praxis gefunden wurde problematisch sind. Die einen dynamischen Ausnahmespezifikation, die sich als nützlich erwies, wurde die unbedingte `throw()` Spezifikation. Um beispielsweise die Funktionsdeklaration:

```cpp
void MyFunction(int i) throw();
```
weist den Compiler an, dass die Funktion keine Ausnahmen auslöst. Allerdings **/Std: c ++ 14** Modus kann dies zu nicht definiertem Verhalten, wenn die Funktion eine Ausnahme auslöst. Aus diesem Grund empfiehlt sich die ["noexcept"](../cpp/noexcept-cpp.md) Operator oben:

```cpp
void MyFunction(int i) noexcept;
```
Die folgende Tabelle enthält die Microsoft C++ Implementierung von Ausnahmespezifikationen:

|Ausnahmespezifikation|Bedeutung|
|-----------------------------|-------------|
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|Die Funktion löst keine Ausnahme aus. In [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) -Modus (der Standardwert ist), `noexcept` und `noexcept(true)` entsprechen. Wenn eine Ausnahme ausgelöst wird, von einer Funktion, die deklariert wird `noexcept` oder `noexcept(true)`, [Std:: Terminate](../standard-library/exception-functions.md#terminate) aufgerufen wird. Wenn eine Ausnahme ausgelöst wird, von einer Funktion deklariert, als `throw()` in **/Std: c ++ 14** Modus wird das Ergebnis ist nicht definiertes Verhalten. Es wird keine bestimmte Funktion aufgerufen. Dies ist eine Abweichung von der C ++ 14-standard, die den Compiler aufzurufende erforderlich [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br/> **Visual Studio 2017 Version 15.5 und höher**: In **/Std: c ++ 17** Modus `noexcept`, `noexcept(true)`, und `throw()` alle gleich sind. In **/Std: c ++ 17** Modus `throw()` ist ein Alias für `noexcept(true)`. In **/Std: c ++ 17** Modus, wenn eine Ausnahme, von einer Funktion deklariert, die mit den Spezifikationen ausgelöst wird [Std:: Terminate](../standard-library/exception-functions.md#terminate) wird aufgerufen, wie für den C ++ 17-standard erforderlich.|
|`noexcept(false)`<br/>`throw(...)`<br/>Keine Angabe|Die Funktion kann einer Ausnahme eines beliebigen Typs.|
|`throw(type)`| (**C ++ 14 und früher**) die Funktion kann eine Ausnahme vom Typ `type`. Der Compiler die Syntax akzeptiert, aber interpretiert ihn als `noexcept(false)`. In **/Std: c ++ 17** Modus der Compiler die Warnung C5040 ausgegeben.|

Wenn Behandlung von Ausnahmen in einer Anwendung verwendet wird, ist eine Funktion in der Aufrufliste, die Ausnahmen ausgelöst, bevor sie mit den äußeren Bereich einer Funktion beenden verarbeitet markiert `noexcept`, `noexcept(true)`, oder `throw()`. Wenn alle Funktionen, die zwischen aufgerufen, die eine Ausnahme auslöst, und derjenigen, die die Ausnahme behandelt werden als angegeben `noexcept`, `noexcept(true)` (oder `throw()` in **/Std: c ++ 17** Modus), das Programm wird beendet, wenn die Noexcept-Funktion gibt die Ausnahme weiter.

Das Verhalten einer Funktion hängt von folgenden Faktoren ab:

- Die [Language standard Kompilierungsmodus](../build/reference/std-specify-language-standard-version.md) festgelegt ist.
- Ob die Funktion mit C oder C++ kompiliert wird.

- Die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption verwendet.

- Ob die Ausnahmespezifikation explizit angegeben wird.

Explizite Ausnahmespezifikationen sind für C-Funktionen nicht zulässig. Eine C-Funktion wird davon ausgegangen, dass nicht Auslösen von Ausnahmen unter **/EHsc**, und eine strukturierte Ausnahmen unter löst möglicherweise **/EHs**, **/EHa**, oder **EHac**.

Die folgende Tabelle enthält, ob eine C++-Funktion möglicherweise unter verschiedenen Optionen der Compiler-Ausnahmebehandlung auslösen:

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

[try-, throw- und catch-Anweisungen (C++)](../cpp/try-throw-and-catch-statements-cpp.md)<br/>
[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)