---
title: "Ausnahmespezifikationen (throw) (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Auslösen von Ausnahmen"
  - "Ausnahmen, Ausnahmespezifikationen"
  - "throw-Schlüsselwort [C++], Ausnahmespezifikationen"
  - "throw-Schlüsselwort [C++], throw() im Vergleich zu throw(...)"
  - "Auslösen von Ausnahmen, throw-Schlüsselwort"
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmespezifikationen (throw) (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausnahmespezifikationen sind eine Sprachfunktion in C\+\+, die in C\+\+11 veraltet ist.  Sie wurden entwickelt, um zusammenfassende Informationen dazu bereitzustellen, welche Ausnahmen aus einer Funktion heraus ausgelöst werden können. In der Praxis stellten sie sich jedoch als problematisch heraus.  Eine Ausnahmespezifikation, die sich als nützlich erwies, war die throw\(\)\-Spezifikation.  Zum Beispiel:  
  
```  
void MyFunction(int i) throw();  
```  
  
 weist den Compiler an, dass die Funktion keine Ausnahmen auslöst.  Dies entspricht der Verwendung von [\_\_declspec \(nothrow\)](../cpp/nothrow-cpp.md).  Seine Verwendung wird als optional erachtet.  
  
 **\(C\+\+11\)** Im ISO C\+\+11\-Standard wurde der Operator [noexcept](../cpp/noexcept-cpp.md) eingeführt, und er wird in Visual Studio 2015 und höher unterstützt.  Verwenden Sie nach Möglichkeit `noexcept`, um anzugeben, ob eine Funktion Ausnahmen auslösen kann.  
  
 Visual C\+\+ folgt bei der Implementierung von Ausnahmespezifikationen nicht dem ISO C\+\+\-Standard.  In der folgenden Tabelle wird die Implementierung von Ausnahmespezifikationen in Visual C\+\+ zusammengefasst.  
  
|Ausnahmespezifikation|Bedeutung|  
|---------------------------|---------------|  
|throw\(\)|Die Funktion löst keine Ausnahme aus.  Wenn jedoch eine Ausnahme von einer mit throw\(\) markierten Funktion ausgelöst wird, erfolgt vom Visual C\+\+\-Compiler kein Aufruf von „unexpected“ \(weitere Informationen dazu erhalten Sie unter [unexpected](../c-runtime-library/reference/unexpected-crt.md) und [unexpected](../Topic/unexpected%20\(%3Cexception%3E\).md)\).  Wenn eine Funktion mit throw\(\) markiert ist, geht der Visual C\+\+\-Compiler davon aus, dass die Funktion keine C\+\+\-Ausnahmen auslöst und entsprechenden Code generiert.  Aufgrund der Code\-Optimierungen, die vom C\+\+\-Compiler ausgeführt werden kann \(auf Grundlage der Annahme, dass die Funktion keine C\+\+\-Ausnahmen auslöst\), wenn eine Funktion eine Ausnahme auslöst, wird das Programm möglicherweise nicht ordnungsgemäß ausgeführt.|  
|throw\(...\)|Die Funktion kann eine Ausnahme auslösen.|  
|throw\(`type`\)|Die Funktion kann eine Ausnahme des Typs `type` auslösen.  Allerdings wird dies in Visual C\+\+ .NET als throw\(...\) interpretiert.  Weitere Informationen erhalten Sie unter [Funktionsausnahmebezeichner](../misc/15-4-function-exception-specifiers.md).|  
  
 Wenn in einer Anwendung die Ausnahmebehandlung verwendet wird, muss es mindestens eine Funktion geben, die ausgelöste Ausnahmen behandelt.  Alle Funktionen, die zwischen derjenigen, die eine Ausnahme auslöst, und derjenigen, die die Ausnahme behandelt, aufgerufen werden, müssen in der Lage sein, die Ausnahme auszulösen.  
  
 Das Auslöseverhalten einer Funktion hängt von den folgenden Faktoren ab:  
  
-   Ob die Funktion mit C oder C\+\+ kompiliert wird.  
  
-   Welche [\/EH](../build/reference/eh-exception-handling-model.md)\-Compileroption verwendet wird.  
  
-   Ob die Ausnahmespezifikation explizit angegeben wird.  
  
 Explizite Ausnahmespezifikationen sind für C\-Funktionen nicht zulässig.  
  
 In der folgenden Tabelle wird das Auslöseverhalten einer Funktion zusammengefasst:  
  
|Funktion|\/EHsc|\/EHs|\/EHa|\/EHac|  
|--------------|------------|-----------|-----------|------------|  
|C\-Funktion|throw\(\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|C\+\+\-Funktion ohne Ausnahmespezifikation|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|C\+\+\-Funktion mit throw\(\)\-Ausnahmespezifikation|throw\(\)|throw\(\)|throw\(...\)|throw\(...\)|  
|C\+\+\-Funktion mit throw\(...\)\-Ausnahmespezifikation|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|C\+\+\-Funktion mit throw\(`type`\)\-Ausnahmespezifikation|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
  
## Beispiel  
  
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
  
  **About to throw 1**  
**in handler**  
**About to throw 1**  
**Caught exception from f4**  
**About to throw 1**  
**in handler**   
## Siehe auch  
 [try\-, throw\- und catch\-Anweisungen \(C\+\+\)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)