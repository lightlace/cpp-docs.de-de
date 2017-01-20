---
title: "Compilerfehler C2469"
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
  - "C2469"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2469"
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2469
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Operator": "Typ"\-Objekt kann nicht zugeordnet werden  
  
 Einem Operator wurde ein ungültiger Typ übergeben.  
  
 Im folgenden Beispiel wird C2469 generiert:  
  
```  
// C2469.cpp int main() { int *i = new void;   // C2469 int *i = new int;   // OK }  
```