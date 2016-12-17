---
title: "Compilerfehler C3409"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3409"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3409"
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3409
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein leerer Attributblock ist nicht erlaubt  
  
 Die eckigen Klammern wurden vom Compiler als [Attributblock](../../windows/cpp-attributes-reference.md) interpretiert, es wurden jedoch keine Attribute gefunden.  
  
 Der Compiler generiert diesen Fehler möglicherweise, wenn Sie eckige Klammern als Teil der Definition eines Lambda\-Ausdrucks verwenden.  Dieser Fehler tritt auf, wenn der Compiler nicht bestimmen kann, ob die eckigen Klammern Teil der Definition eines Lambda\-Ausdrucks oder eines Attributblocks sind.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md).  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn die eckigen Klammern Teil eines Attributblocks sind:  
  
    1.  Stellen Sie ein oder mehrere Attribute im Attributblock bereit.  
  
    2.  Entfernen Sie den Attributblock.  
  
2.  Wenn die eckigen Klammern Teil eines Lambda\-Ausdrucks sind:  
  
    1.  Stellen Sie sicher, dass der Lambda\-Ausdruck gültigen Syntaxregeln folgt.  
  
         Weitere Informationen zur Lambda\-Ausdruckssyntax finden Sie unter [Lambda\-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3409 generiert.  
  
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
  
## Beispiel  
 Im folgenden Beispiel wird C3409 generiert, da ein Lambda\-Ausdruck die `mutable`\-Spezifikation verwendet, aber keine Parameterliste bereitstellt.  Der Compiler kann nicht bestimmen, ob die eckigen Klammern Teil der Definition eines Lambda\-Ausdrucks oder eines Attributblocks sind.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## Siehe auch  
 [Attribut](../../windows/cpp-attributes-reference.md)   
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)   
 [Lambda\-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md)