---
title: Compilerfehler Fehler C2659 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2659
dev_langs:
- C++
helpviewer_keywords:
- C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b01afeaaa82ed772f5d812f36b3de0aac24679a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2659"></a>Compilerfehler Fehler C2659
„Operator“: Überladene Funktion als linker Operand  
  
 Eine Funktion steht auf der linken Seite des angegebenen Operators. Der häufigste Grund für diesen Fehler ist, dass der Compiler den Bezeichner auf der linken Seite des Operators als Funktion analysiert hat, während der Entwickler ihn als Variable vorsah. Weitere Informationen finden Sie im Wikipedia Artikel [am ärgerlich Analyse](http://en.wikipedia.org/wiki/Most_vexing_parse). Dieses Beispiel demonstriert, dass die Deklaration einer Funktion und die Definition einer Variablen leicht miteinander verwechselt werden können:  
  
```  
// C2659a.cpp  
// Compile using: cl /W4 /EHsc C2659a.cpp  
#include <string>  
using namespace std;  
  
int main()   
{  
   string string1(); // string1 is a function returning string  
   string string2{}; // string2 is a string initialized to empty   
  
   string1 = "String 1"; // C2659  
   string2 = "String 2";  
}  
```  
  
 Ändern Sie zur Behebung dieses Problems die Deklaration des Bezeichners so, dass er nicht als Funktionsdeklaration analysiert wird.  
  
 Fehler C2659 kann auch auftreten, wenn die Funktion einen Typ aufweist, der nicht im Ausdruck auf der linken Seite des angegebenen Operators verwendet werden kann. In diesem Beispiel wird der Fehler C2659 erzeugt, wenn der Code einer Funktion einen Funktionszeiger zuweist:  
  
```  
// C2659b.cpp  
// Compile using: cl /W4 /EHsc C2659b.cpp  
int func0(void) { return 42; }  
int (*func1)(void);  
  
int main()  
{  
   func1 = func0;  
   func0 = func1; // C2659  
}  
```