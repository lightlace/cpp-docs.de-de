---
title: "Compilerfehler C2482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2482"
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Dynamische Initialisierung von 'thread'\-Daten nicht zulässig  
  
 Variablen, die mit dem `thread`\-Attribut deklariert wurden, können nicht mit einem Ausdruck initialisiert werden, der eine Auswertung zur Laufzeit erfordert.  Es muss ein statischer Ausdruck verwendet werden, um `thread`\-Daten zu initialisieren.  
  
 Im folgenden Beispiel wird C2482 generiert:  
  
```  
// C2482.cpp  
// compile with: /c  
#define Thread __declspec( thread )  
Thread int tls_i = tls_i;   // C2482  
  
int j = j;   // OK in C++; C error  
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
```