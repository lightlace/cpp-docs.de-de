---
title: "Compilerfehler C2142"
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
  - "C2142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2142"
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterschiedliche Funktionsdeklarationen, nur eine definiert eine variable Parameterliste  
  
 Eine Deklaration der Funktion enthält eine Liste variabler Parameter.  Bei einer anderen Deklaration ist dies nicht der Fall.  Nur ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
 Im folgenden Beispiel wird C2142 generiert:  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```