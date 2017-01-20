---
title: "Compilerfehler C2998"
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
  - "C2998"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2998"
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2998
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„identifier“: Kann keine Vorlagendefinition sein.  
  
 Der Compiler konnte die in der Vorlagendefinition verwendete Syntax nicht verarbeitet.  
  
 Im folgenden Beispiel wird C2998 generiert:  
  
```  
// C2998.cpp // compile with: /c template <class T> int x = 1018; // C2998  
```