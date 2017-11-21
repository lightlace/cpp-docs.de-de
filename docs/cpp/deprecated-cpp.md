---
title: veraltet (C++) | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: deprecated_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3ec06d469f6fc71b23c9bdc6a67e5ed741d9f5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="deprecated-c"></a>deprecated (C++)
In diesem Thema geht es um die Microsoft-spezifische Declspec Deklaration veraltet. Informationen zu den C ++ 14 `[[deprecated]]` -Attribut, und eine Anleitung für dieses Attribut im Vergleich zu den Microsoft-spezifische Declspec oder Pragma verwenden finden Sie unter [Standard C++-Attribute](attributes2.md).

 Mit den nachfolgenden Ausnahmen der **veraltet** Deklaration bietet die gleiche Funktionalität wie die [veraltet](../preprocessor/deprecated-c-cpp.md) Pragma:  
  
-   Die **veraltet** Deklaration können Sie bestimmte Arten von funktionsüberladungen als veraltet angeben, wohingegen das Pragma auf alle überladenen Arten eines Funktionsnamens angewendet wird.  
  
-   Die **veraltet** Deklaration ermöglicht die Angabe eine Nachricht, die zur Kompilierzeit angezeigt wird. Der Text der Meldung kann von einem Makro stammen.  
  
-   Makros können nur als mit veraltet gekennzeichnet werden die **veraltet** Pragma.  
  
 Findet der Compiler die Verwendung der einen veralteten Bezeichner oder Standard [ `[[deprecated]]` ](attributes2.md) -Attribut, eine [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) Warnung wird ausgelöst.  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="example"></a>Beispiel  
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
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)