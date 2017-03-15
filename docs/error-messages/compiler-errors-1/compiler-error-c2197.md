---
title: "Compilerfehler C2197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2197"
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion": Zu viele Argumente für Aufruf  
  
 Der Compiler hat zu viele Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.  
  
 Im folgenden Beispiel wird C2197 generiert:  
  
```  
// C2197.c // compile with: /Za /c void func( int ); int main() { func( 1, 2 );   // C2197 two actual parameters func( 2 );   // OK }  
```