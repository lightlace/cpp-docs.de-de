---
title: "Compilerfehler C2400"
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
  - "C2400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2400"
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inlineassembler: Syntaxfehler in 'Kontext'; 'Token' gefunden  
  
 Das Token hat einen Syntaxfehler im angegebenen Kontext verursacht.  
  
 Im folgenden Beispiel wird C2400 generiert:  
  
```  
// C2400.cpp  
// processor: x86  
int main() {  
   __asm {  
      heh ax,bx;   // C2400, heh is not a valid x86 instruction  
      mov ax,bx;   // OK  
   }  
}  
```