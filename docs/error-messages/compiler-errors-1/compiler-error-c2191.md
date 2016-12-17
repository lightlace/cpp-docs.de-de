---
title: "Compilerfehler C2191"
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
  - "C2191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2191"
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zweite Parameterliste länger als erste Liste  
  
 Eine C\-Funktion wurde ein zweites Mal deklariert, wobei eine längere Parameterliste angegeben wurde.  C unterstützt keine überladenen Funktionen.  
  
## Beispiel  
 Im folgenden Beispiel wird C2191 generiert:  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```