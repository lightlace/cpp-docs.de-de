---
title: "Compilerfehler C2197"
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
  - "C2197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2197"
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion": Zu viele Argumente für Aufruf  
  
 Der Compiler hat zu viele Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.  
  
 Im folgenden Beispiel wird C2197 generiert:  
  
```  
// C2197.c // compile with: /Za /c void func( int ); int main() { func( 1, 2 );   // C2197 two actual parameters func( 2 );   // OK }  
```