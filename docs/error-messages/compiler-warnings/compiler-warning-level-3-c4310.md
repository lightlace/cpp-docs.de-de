---
title: "Compilerwarnung (Stufe 3) C4310"
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
  - "C4310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4310"
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typumwandlung verkürzt konstante Werte  
  
 Ein konstanter Wert wird in einen kleineren Typ umgewandelt.  Die Typumwandlung, durch die die Daten verkürzt werden, wird vom Compiler vorgenommen.  Im folgenden Beispiel wird C4310 generiert:  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```