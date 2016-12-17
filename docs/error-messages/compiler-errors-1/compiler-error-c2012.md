---
title: "Compilerfehler C2012"
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
  - "C2012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2012"
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dateiname nach "\<" fehlt  
  
 In einer `#include`\-Direktive fehlt der erforderliche Dateiname.  
  
 Im folgenden Beispiel wird C2012 generiert:  
  
```  
// C2012.cpp #include <   // C2012 include the filename to resolve  
```  
  
 Mögliche Lösung:  
  
```  
// C2012b.cpp // compile with: /c #include <stdio.h>  
```