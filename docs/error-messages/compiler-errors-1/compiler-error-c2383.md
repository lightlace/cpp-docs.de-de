---
title: "Compilerfehler C2383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2383"
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Für dieses Symbol sind Standardargumente nicht zulässig  
  
 Der C\+\+\-Compiler unterstützt keine Standardargumente für Zeiger auf Funktionen.  
  
 Dieser Code wurde vom Compiler der vorherigen Version akzeptiert, generiert jetzt aber einen Fehler.  Bei Code, der von allen Visual C\+\+\-Versionen unterstützt wird, sollte einem Argument mit einem Zeiger auf eine Funktion kein Standardwert zugewiesen werden.  
  
 In der folgenden Zeile wird C2383 generiert:  
  
```  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```