---
title: "Compilerfehler C2177"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2177"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2177"
ms.assetid: 2a39a880-cddb-4d3e-a572-645a14c4c478
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2177
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konstante zu groß  
  
 Ein konstanter Wert ist zu groß für den Variablentyp, dem er zugewiesen ist.  
  
 Im folgenden Beispiel wird C2177 generiert:  
  
```  
// C2177.cpp int main() { int a=18446744073709551616;   // C2177 int b=18446744073709551615;   // OK }  
```