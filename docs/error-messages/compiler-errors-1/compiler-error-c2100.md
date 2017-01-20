---
title: "Compilerfehler C2100"
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
  - "C2100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2100"
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeigeroperation ungültig  
  
 Der Dereferenzierungsoperator \(`*` \) wurde mit einem Wert verwendet, der kein Zeiger ist.  
  
 Im folgenden Beispiel wird C2100 generiert:  
  
```  
// C2100.cpp  
int main() {  
   int r = 0, *s = 0;  
   s = &r;  
   *r = 200;   // C2100  
   *s = 200;   // OK  
}  
```