---
title: "deprecated (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "deprecated"
  - "deprecated_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], deprecated"
  - "deprecated __declspec-Schlüsselwort"
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# deprecated (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(Microsoft\-spezifisch\) Mit den nachfolgenden Ausnahmen bietet die Deklaration **deprecated** dieselbe Funktionalität wie das [deprecated](../preprocessor/deprecated-c-cpp.md)\-Pragma:  
  
-   Mit der Deklaration **deprecated** können Sie bestimmte Arten von Funktionsüberladungen als veraltet angeben, wohingegen das Pragma auf alle überladenen Arten eines Funktionsnamens angewendet wird.  
  
-   Mit der Deklaration **deprecated** können Sie eine Meldung angeben, die zur Kompilierzeit angezeigt wird.  Der Text der Meldung kann von einem Makro stammen.  
  
-   Makros können nur mit dem **deprecated**\-Pragma als veraltet gekennzeichnet werden.  
  
 Trifft der Compiler auf einen veralteten Bezeichner, wird eine [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)\-Warnung ausgelöst.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Funktionen als veraltet gekennzeichnet werden und wie eine Meldung angegeben wird, die bei Verwendung einer veralteten Funktion zur Kompilierzeit angezeigt wird.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Klassen als veraltet gekennzeichnet werden und wie eine Meldung angegeben wird, die bei Verwendung einer veralteten Klasse zur Kompilierzeit angezeigt wird.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)