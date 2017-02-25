---
title: "Compilerfehler C2467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2467"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2467"
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2467
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deklaration des anonymen selbst definierten Typs 'benutzerdefinierter Typ' unzulässig  
  
 Es wurde ein geschachtelter benutzerdefinierter Typ deklariert.  Dieser Fehler tritt auf, wenn Sie C\-Quellcode mit aktivierter ANSI\-Kompatibilitätsoption \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) kompilieren.  
  
 Im folgenden Beispiel wird C2467 generiert:  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```