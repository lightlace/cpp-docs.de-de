---
title: "Compilerfehler C2190 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2190"
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erste Parameterliste länger als zweite Liste  
  
 Eine C\-Funktion wurde ein zweites Mal deklariert, wobei eine kürzere Parameterliste angegeben wurde.  C unterstützt keine überladenen Funktionen.  
  
 Im folgenden Beispiel wird C2190 generiert:  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```