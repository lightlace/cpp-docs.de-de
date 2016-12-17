---
title: "Compilerfehler C3452"
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
  - "C3452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3452"
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Listenargumentmember ist keine Konstante.  
  
 Ein Argument wurde an ein Attribut übergeben, das eine Konstante erwartet hat, d. h. einen Wert, der zur Kompilierzeit ausgewertet werden kann.  
  
## Beispiel  
 Im folgenden Beispiel wird C3452 generiert:  
  
```  
// C3452.cpp // compile with: /c int i; [module( name="mod", type=dll, custom={i} ) ];   // C3452 // try the following line instead // [module( name="mod", type=dll, custom={"a"} ) ];  
```