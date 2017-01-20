---
title: "Compilerfehler C2246"
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
  - "C2246"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2246"
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2246
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„identifier“: Ungültiger statischer Datenmember in lokal definierter Klasse  
  
 Ein Member einer Klasse, Struktur oder Union mit lokalem Gültigkeitsbereich wurde als `static` deklariert.  
  
 Im folgenden Beispiel wird C2246 generiert:  
  
```  
// C2246.cpp // compile with: /c void func( void ) { class A { static int i; };   // C2246  i is local to func static int j;   // OK };  
```