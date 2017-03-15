---
title: "Compilerfehler C3669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3669"
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' : Überschreibungsbezeichner 'override' ist in statischen Funktionen oder Konstruktoren nicht zulässig  
  
 Eine Override wurde falsch angegeben.  Weitere Informationen finden Sie unter [Explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3669 generiert.  
  
```  
// C3669.cpp  
// compile with: /clr  
public ref struct R {  
   R() override {}   // C3669  
};  
```