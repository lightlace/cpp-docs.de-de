---
title: "Schwerwiegender Fehler C1019"
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
  - "C1019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1019"
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes \#else  
  
 Die `#else`\-Direktive befindet sich außerhalb eines `#if`\-, `#ifdef`\- oder `#ifndef`\-Konstrukts. Verwenden Sie `#else` nur innerhalb eines dieser Konstrukte.  
  
 Im folgenden Beispiel wird C1019 generiert:  
  
```  
// C1019.cpp #else   // C1019 #endif int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1019b.cpp #if 1 #else #endif int main() {}  
```