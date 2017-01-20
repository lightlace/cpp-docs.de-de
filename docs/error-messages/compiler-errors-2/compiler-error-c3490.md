---
title: "Compilerfehler C3490"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3490"
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var" kann nicht geändert werden, da über ein Konstantenobjekt darauf zugegriffen wird  
  
 Ein Lambda\-Ausdruck, der in einer `const`\-Methode deklariert ist, kann nicht änderbare Memberdaten nicht ändern.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `const`\-Modifizierer aus der Methodendeklaration.  
  
## Beispiel  
 Im folgenden Beispiel wird C3490 generiert, da die Membervariable `_i` in einer `const`\-Methode geändert wird:  
  
```  
// C3490a.cpp // compile with: /c class C { void f() const  { auto x = [=]() { _i = 20; }; // C3490 } int _i; };  
```  
  
## Beispiel  
 Im folgende Beispiel wird C3490 durch Entfernen des `const`\-Modifizierers aus der Methodendeklaration aufgelöst:  
  
```  
// C3490b.cpp // compile with: /c class C { void f() { auto x = [=]() { _i = 20; }; } int _i; };  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)