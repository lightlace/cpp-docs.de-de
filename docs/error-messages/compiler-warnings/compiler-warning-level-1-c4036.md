---
title: "Compilerwarnung (Stufe 1) C4036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4036"
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 1) C4036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unbenannter Typ 'Typ' als übergebener Parameter  
  
 Für eine Struktur, Union, Enumeration oder Klasse, die als übergebener Parameter verwendet wurde, ist kein Typname angegeben. Wenn Sie [\/Zg](../../build/reference/zg-generate-function-prototypes.md) zum Generieren von Funktionsprototypen verwenden, gibt der Compiler diese Warnung aus und kommentiert den formalen Parameter im generierten Prototyp aus.  
  
 Geben Sie einen Typnamen an, um diese Warnung zu vermeiden.  
  
## Beispiel  
 Im folgenden Beispiel wird C4036 generiert:  
  
```  
// C4036.c // compile with: /Zg /W1 // D9035 expected typedef struct { int i; } T; void f(T* t) {}   // C4036 // OK typedef struct MyStruct { int i; } T2; void f2(T2 * t) {}  
```