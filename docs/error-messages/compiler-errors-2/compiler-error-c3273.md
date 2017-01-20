---
title: "Compilerfehler C3273"
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
  - "C3273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3273"
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_finally' kann nicht für einen Ausnahmeblock in nicht verwaltetem Code verwendet werden.  
  
 Im folgenden Beispiel wird C3273 generiert:  
  
```  
// C3273.cpp // compile with: /GX int main() { try { } catch (int) { } __finally   // C3273, remove __finally clause { } }  
```