---
title: "Compilerfehler C2153"
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
  - "C2153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2153"
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hexadezimale Konstanten müssen mindestens eine hexadezimale Ziffer enthalten  
  
 Die Hexadezimalkonstanten **0x**, **0X** und **\\x** sind unzulässig.  Auf **x** oder **X** muss mindestens eine hexadezimale Ziffer folgen.  
  
 Im folgenden Beispiel wird C2153 generiert:  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```