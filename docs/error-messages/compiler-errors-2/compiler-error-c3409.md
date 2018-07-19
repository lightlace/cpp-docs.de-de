---
title: Compilerfehler C3409 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1964cffd0593e87a790befd8a76ae13847f2058d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257269"
---
# <a name="compiler-error-c3409"></a>Compilerfehler C3409
ein leerer Attributblock ist nicht zulässig.  
  
 Der rechteckigen Klammern wurden durch den Compiler als interpretiert eine [Attribut](../../windows/cpp-attributes-reference.md) blockieren, aber keine Attribute gefunden wurden.  
  
 Der Compiler kann dieser Fehler generiert, wenn Sie eckige Klammern als Teil der Definition eines Lambda-Ausdrucks verwenden. Dieser Fehler tritt auf, wenn der Compiler nicht ermitteln kann, ob der rechteckigen Klammern Teil der Definition eines Lambda-Ausdrucks oder ein Attributblock sind. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../cpp/lambda-expressions-in-cpp.md).  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wenn der rechteckigen Klammern ein Attributblock gehören:  
  
    1.  Geben Sie ein oder mehrere Attribute im Attributblock.  
  
    2.  Entfernen Sie den Attributblock.  
  
2.  Wenn der rechteckigen Klammern Teil einen Lambda-Ausdruck sind:  
  
    1.  Stellen Sie sicher, dass der Lambda-Ausdruck gültiger Syntaxregeln befolgt.  
  
         Weitere Informationen zu Lambda-Ausdruckssyntax, finden Sie unter [Lambda-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).  
  
    2.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3409 generiert.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3409 generiert, da ein Lambda-Ausdruck verwendet die `mutable` -Spezifikation, jedoch keine Parameterliste enthält. Der Compiler kann nicht ermitteln, ob der rechteckigen Klammern Teil der Definition eines Lambda-Ausdrucks oder ein Attributblock sind.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Attribut](../../windows/cpp-attributes-reference.md)   
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)   
 [Lambdaausdruckssyntax](../../cpp/lambda-expression-syntax.md)