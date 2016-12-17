---
title: "Compilerfehler C2110"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2110"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2110"
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2110
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„\+“: Zwei Zeiger können nicht addiert werden.  
  
 Es wurde versucht, zwei Zeigerwerte mit dem Plus\-Operator \(`+`\) zu addieren.  
  
 Im folgenden Beispiel wird C2110 generiert:  
  
```  
// C2110.cpp int main() { int a = 0; int *pa; int *pb; a = pa + pb;   // C2110 }  
```