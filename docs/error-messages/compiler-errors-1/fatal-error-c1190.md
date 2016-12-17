---
title: "Schwerwiegender Fehler C1190"
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
  - "C1190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1190"
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Für verwalteten Zielcode ist eine \/clr\-Option erforderlich.  
  
 Sie verwenden CLR\-Konstrukte, aber Sie haben keine **\/clr** angegeben.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Im folgenden Beispiel wird C1190 generiert:  
  
```  
// C1190.cpp // compile with: /c __gc class A {};   // C1190 ref class A {};  
```