---
title: "Compilerfehler C2137"
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
  - "C2137"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2137"
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2137
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

leere Zeichenkonstante  
  
 Die leere Zeichenkonstante \(' '\) ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2137 generiert:  
  
```  
// C2137.cpp int main() { char c = '';   // C2137 char d = ' ';   // OK }  
```