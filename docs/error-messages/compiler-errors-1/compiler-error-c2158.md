---
title: "Compilerfehler C2158"
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
  - "C2158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2158"
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Die \#pragma make\_public\-Direktive wird derzeit nur für systemeigene Nichtvorlagentypen unterstützt  
  
 Das Pragma [make\_public](../../preprocessor/make-public.md) kann nur auf systemeigene Nichtvorlagentypen angewendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2158 generiert.  
  
```  
// C2158.cpp // compile with: /clr /c ref class A {}; #pragma make_public(A)   // C2158 template< typename T > class B {}; #pragma make_public(B)   // C2158 #pragma make_public(B<int>)   // C2158 void C () {} #pragma make_public(C)   // C2158 class D {}; #pragma make_public(D)   // OK  
```