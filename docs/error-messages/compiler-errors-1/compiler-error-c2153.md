---
title: "Compilerfehler C2153 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2153"
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
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