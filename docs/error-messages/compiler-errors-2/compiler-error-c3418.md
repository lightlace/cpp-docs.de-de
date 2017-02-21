---
title: "Compilerfehler C3418 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3418"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3418"
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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