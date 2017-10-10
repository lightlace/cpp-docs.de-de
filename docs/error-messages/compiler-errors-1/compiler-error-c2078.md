---
title: Compilerfehler Fehler C2078 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6ae181d68f0487f663febfbe38fa42af8670b28
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2078"></a>Compilerfehler Fehler C2078
Zu viele Initialisierungen  
  
 Die Anzahl der Initialisierungen überschreitet die Anzahl der zu initialisierenden Objekte.  
  
 Wenn die innere Klammern aus der Initialisiererliste entfernt werden, kann der Compiler die richtige Zuweisung der Initialisierer für Objekte und interne Objekte ableiten. Durch vollständige Klammern werden Mehrdeutigkeiten beseitigt und somit Ergebnisse in der richtigen Zuweisung angezeigt. Teilweise Klammern lösen möglicherweise C2087 aufgrund von Mehrdeutigkeit in der Zuweisung des Initialisierers für Objekte aus.  
  
 Im folgenden Beispiel wird C2078 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2078.cpp  
// Compile by using: cl /c /W4 C2078.cpp  
struct S {  
   struct {  
      int x, y;  
   } z[2];  
};  
  
int main() {  
   int d[2] = {1, 2, 3};   // C2078  
   int e[2] = {1, 2};      // OK  
  
   char a[] = {"a", "b"};  // C2078  
   char *b[] = {"a", "b"}; // OK  
   char c[] = {'a', 'b'};  // OK  
  
   S s1{1, 2, 3, 4};       // OK  
   S s2{{1, 2}, {3, 4}};   // C2078  
   S s3{{1, 2, 3, 4}};     // OK  
   S s4{{{1, 2}, {3, 4}}}; // OK  
}  
  
```
