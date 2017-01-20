---
title: "Compilerwarnung (Stufe 1) C4178"
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
  - "C4178"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4178"
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4178
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die case\-Konstante 'Konstante' ist zu groß für den Typ des switch\-Ausdrucks.  
  
 Eine case\-Konstante in einem `switch`\-Ausdruck passt nicht in den Typ, dem sie zugewiesen ist.  
  
## Beispiel  
  
```  
// C4178.cpp // compile with: /W1 int main() { int i;  // maximum size of unsigned long int is 4294967295 switch( i ) { case 4294967295:   // OK break; case 4294967296:   // C4178 break; } }  
```