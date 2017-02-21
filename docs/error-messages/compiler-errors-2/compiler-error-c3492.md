---
title: "Compilerfehler C3492 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3492"
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Ein Member einer anonymen Union kann nicht erfasst werden.  
  
 Sie können ein Member einer unbenannten Union nicht erfassen.  
  
### So beheben Sie diesen Fehler  
  
-   Weisen Sie der Union einen Namen zu, und übergeben Sie die vollständige Union\-Struktur an die Erfassungsliste des Lambdaausdrucks.  
  
## Beispiel  
 Im folgenden Beispiel wird C3492 generiert, da ein Member einer anonymen Union erfasst wird:  
  
```  
// C3492a.cpp int main() { union { char ch; int x; }; ch = 'y'; [&x](char ch) { x = ch; }(ch); // C3492 }  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3492 behoben, indem der Union ein Name zugewiesen und die vollständige Union\-Struktur an die Erfassungsliste des Lambdaausdrucks übergeben wird.  
  
```  
// C3492b.cpp int main() { union { char ch; int x; } u; u.ch = 'y'; [&u](char ch) { u.x = ch; }(u.ch); }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)