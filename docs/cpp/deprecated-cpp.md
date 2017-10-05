---
title: veraltet (C++) | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- deprecated
- deprecated_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9ac25648e2d19da82f6c213992699c237e05c01e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
