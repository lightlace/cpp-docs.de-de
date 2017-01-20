---
title: "Compilerfehler C2182"
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
  - "C2182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2182"
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bezeichner': Unzulässige Verwendung des Typs 'void'  
  
 Eine Variable ist als Typ `void` deklariert.  
  
 Im folgenden Beispiel wird C2182 generiert:  
  
```  
// C2182.cpp // compile with: /c int main() { int i = 10; void &ir = i;   // C2182 cannot have a reference to type void int &ir = i;   // OK }  
```