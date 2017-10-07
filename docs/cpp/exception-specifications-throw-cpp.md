---
title: Ausnahmespezifikationen (Throw) (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6577cf489ee1c9d64689938bb8a12660cec96893
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="exception-specifications-throw-noexcept-c"></a>Ausnahmespezifikationen (Throw, Noexcept) (C++)
Ausnahmespezifikationen sind eine Sprachfunktion in C++, die der Programmierer die Ausnahmetypen angeben, die von einer Funktion weitergegeben werden können. Sie können angeben, dass eine Funktion kann nicht mithilfe von einer Ausnahme beendet ggf. ein *Ausnahmespezifikation*. Der Compiler kann diese Informationen verwenden, um die Aufrufe an die Funktion zu optimieren und versieht die Funktion zum Beenden des Programms, wenn eine unerwartete Ausnahme. Es gibt zwei Arten von Ausnahmespezifikation. Die *Noexcept-Spezifikation* ist neu in C ++ 11. Es gibt an, ob der Satz der möglichen Ausnahmen, die überwechseln können, dass Sie die Funktion leer ist. Die *dynamische Ausnahmespezifikation*, oder `throw(optional_type_list)` -Spezifikation ist in C ++ 11 veraltet und wird von Visual Studio nur teilweise unterstützt. Diese Ausnahmespezifikation wurde entworfen, um zusammenfassende Informationen dazu, welche Ausnahmen können, aus einer Funktion ausgelöst werden bereitzustellen, aber in der Praxis befand er sich problematisch sein. Eine dynamische Ausnahmespezifikation, die sich als nützlich erwies wurde die unbedingte `throw()` Spezifikation. Um beispielsweise die Funktionsdeklaration:  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 weist den Compiler an, dass die Funktion keine Ausnahmen auslöst. Dies entspricht dem mit [__declspec(nothrow)](../cpp/nothrow-cpp.md). Seine Verwendung wird als optional erachtet.  
  
Im ISO C ++ 11-Standard der [Noexcept](../cpp/noexcept-cpp.md) Operator als Ersatz eingeführt wurde. Es wird in Visual Studio 2015 und höher unterstützt. Verwenden Sie nach Möglichkeit eine `noexcept` Ausdruck angeben, ob eine Funktion Ausnahmen auslösen kann. Verwenden Sie beispielsweise diese Funktionsdeklaration anstelle oben:  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Während der Visual C++ bietet uneingeschränkte Unterstützung der `noexcept` Ausdruck von der ISO C++-Standard in seiner Implementierung von Ausnahmespezifikationen dynamische ausfährt.  In der folgenden Tabelle wird die Implementierung von Ausnahmespezifikationen in Visual C++ zusammengefasst.  
  
|Ausnahmespezifikation|Bedeutung|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|Die Funktion löst keine Ausnahme aus. Jedoch, wenn eine Ausnahme, aus einer Funktion, die markiert ausgelöst wird `throw()`, der Visual C++-Compiler ruft `std::terminate`, nicht `std::unexpected`. Finden Sie unter [std::unexpected](../c-runtime-library/reference/unexpected-crt.md) für Weitere Informationen. Wenn eine Funktion gekennzeichnet ist `noexcept`, `noexcept(true)`, oder `throw()`, Visual C++-Compiler geht davon aus, dass die Funktion keine C++-Ausnahmen auslöst und generiert den Code entsprechend. Da codeoptimierungen, die ausgeführt werden können, durch die C++-Compiler, die basierend auf der Annahme, dass die Funktion keine C++-Ausnahmen auslöst, wenn eine Funktion eine Ausnahme auslöst, wird das Programm möglicherweise nicht ordnungsgemäß ausgeführt.|  
|`noexcept(false)`<br/>`throw(...)`<br/>Keine Angabe|Die Funktion kann eine Ausnahme eines beliebigen Typs.|  
|`throw(type)`|Die Funktion kann eine Ausnahme des Typs `type` auslösen. In Visual C++ diese Syntax wird akzeptiert, aber als interpretiert `noexcept(false)`.|  
  
 Behandlung von Ausnahmen in einer Anwendung verwendet, es muss eine Funktion in der Aufrufliste, die Handles Ausnahmen ausgelöst, bevor sie den äußeren Bereich einer Funktion beendet markiert `noexcept`, `noexcept(true)`, oder `throw()`. Wenn alle Funktionen zwischen aufgerufen derjenige, der eine Ausnahme auslöst und das Projekt, das die Ausnahme behandelt werden als angegeben `noexcept`, `noexcept(true)`, oder `throw()`, das Programm beendet wird, wenn die Ausnahme, die Noexcept-Funktion verteilt.  
  
 Das Ausnahmeverhalten einer Funktion hängt von den folgenden Faktoren ab:  
  
-   Ob die Funktion mit C oder C++ kompiliert wird.  
  
-   Die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption verwendet.  
  
-   Ob die Ausnahmespezifikation explizit angegeben wird.  
  
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
 [try-, throw- und catch-Anweisungen (C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
