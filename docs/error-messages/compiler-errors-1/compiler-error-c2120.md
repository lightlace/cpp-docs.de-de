---
title: "Compilerfehler C2120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2120"
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
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