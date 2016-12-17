---
title: "Compilerfehler C3232"
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
  - "C3232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3232"
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Param': Ein generischer Typparameter kann nicht in einem qualifizierten Namen verwendet werden.  
  
 Ein generischer Typparameter wurde nicht ordnungsgemäß verwendet.  
  
 Im folgenden Beispiel wird C3232 generiert:  
  
```  
// C3232.cpp // compile with: /clr generic <class T> ref class C { typename T::TYPE t;   // C3232 };  
```