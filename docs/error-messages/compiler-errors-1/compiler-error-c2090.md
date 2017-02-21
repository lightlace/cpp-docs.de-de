---
title: "Compilerfehler C2090 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2090"
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktionsergebnis ist ein Array  
  
 Eine Funktion kann kein Array zurückgeben.  Stattdessen sollte ein Zeiger auf ein Array zurückgegeben werden.  
  
 Im folgenden Beispiel wird C2090 generiert:  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 Mögliche Lösung:  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```