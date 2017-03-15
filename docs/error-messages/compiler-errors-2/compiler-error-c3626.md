---
title: "Compilerfehler C3626 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3626"
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort': Das '\_\_event'\-Schlüsselwort kann nur bei COM\-Schnittstellen, Memberfunktionen und Datenmembern, die Zeiger auf Delegate sind, verwendet werden  
  
 Ein Schlüsselwort wurde falsch verwendet.  
  
 Im folgenden Beispiel wird C3626 generiert:  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```