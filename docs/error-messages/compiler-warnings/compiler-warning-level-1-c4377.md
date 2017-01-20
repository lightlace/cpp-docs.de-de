---
title: "Compilerwarnung (Stufe 1) C4377"
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
  - "C4377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4377"
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Systemeigene Typen sind standardmäßig privat; \-d1PrivateNativeTypes ist veraltet  
  
 In früheren Versionen waren systemeigene Typen in Assemblys standardmäßig öffentlich. Mit einer internen und nicht dokumentierten Compileroption \(**\/d1PrivateNativeTypes**\) wurden sie in privat umgewandelt.  
  
 Alle Typen, systemeigen und CLR, sind nun in einer Assembly standardmäßig privat, sodass **\/d1PrivateNativeTypes** nicht mehr benötigt wird.  
  
## Beispiel  
 Im folgenden Beispiel wird C4377 generiert.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```