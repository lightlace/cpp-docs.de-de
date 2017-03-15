---
title: "Schwerwiegender Fehler C1019 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1019"
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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