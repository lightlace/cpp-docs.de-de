---
title: "Compilerfehler C3418"
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
  - "C3418"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3418"
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3418
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Zugriffsspezifizierer "Spezifizierer" wird nicht unterstützt.  
  
 Ein CLR\-Zugriffsspezifizierer wurde falsch angegeben.  Weitere Informationen finden Sie unter [Typ\- und Membersichtbarkeit](../../misc/type-and-member-visibility.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3418 generiert:  
  
```  
// C3418.cpp // compile with: /clr /c ref struct m { internal public:   // C3418 void test(){} }; ref struct n { internal:   // OK void test(){} };  
```