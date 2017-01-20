---
title: "Schwerwiegender Fehler C1018"
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
  - "C1018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1018"
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes \#elif  
  
 Die `#elif`\-Direktive befindet sich außerhalb eines `#if`\-, `#ifdef`\- oder `#ifndef`\-Konstrukts. Verwenden Sie `#elif` nur innerhalb eines dieser Konstrukte.  
  
 Im folgenden Beispiel wird C1018 generiert:  
  
```  
// C1018.cpp #elif      // C1018 #endif int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1018b.cpp #if 1 #elif #endif int main() {}  
```