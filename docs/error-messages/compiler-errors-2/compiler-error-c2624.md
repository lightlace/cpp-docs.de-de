---
title: "Compilerfehler C2624"
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
  - "C2624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2624"
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lokale Klassen können nicht zum Deklarieren von externen Variablen verwendet werden  
  
 Eine lokale Klasse oder Struktur kann nicht zum Deklarieren von `extern`\-Variablen verwendet werden.  
  
 Im folgenden Beispiel wird C2624 generiert:  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```