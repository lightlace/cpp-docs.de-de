---
title: "Compilerfehler C2192 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2192"
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parameterdeklaration 'Nummer' ist unterschiedlich  
  
 Eine C\-Funktion wurde ein zweites Mal deklariert, wobei eine andere Parameterliste angegeben wurde.  C unterstützt keine überladenen Funktionen.  
  
 Im folgenden Beispiel wird C2192 generiert:  
  
```  
// C2192.c  
// compile with: /Za /c  
void func( float, int );  
void func( int, float );   // C2192, different parameter list  
void func2( int, float );   // OK  
```