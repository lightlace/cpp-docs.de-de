---
title: "Compilerfehler C2196"
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
  - "C2196"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2196"
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2196
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der case\-Wert 'Wert' wird bereits verwendet.  
  
 Eine switch\-Anweisung verwendet denselben case\-Wert mehrmals.  
  
 Im folgenden Beispiel wird C2196 generiert:  
  
```  
// C2196.cpp int main() { int i = 0; switch( i ) { case 0: break; case 0:   // C2196 // try the following line instead // case 1: break; } }  
```