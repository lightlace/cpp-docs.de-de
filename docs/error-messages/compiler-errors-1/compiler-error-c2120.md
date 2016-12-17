---
title: "Compilerfehler C2120"
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
  - "C2120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2120"
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"void" mit Typen nicht zulässig  
  
 Innerhalb einer Deklaration wurde der `void`\-Typ zusammen mit einem anderen Typ verwendet.  
  
 Im folgenden Beispiel wird C2120 generiert:  
  
```  
// C2120.cpp  
int main() {  
   void int i;   // C2120  
   int j;   // OK  
}  
```