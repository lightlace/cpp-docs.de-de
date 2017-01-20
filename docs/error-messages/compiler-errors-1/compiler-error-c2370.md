---
title: "Compilerfehler C2370"
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
  - "C2370"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2370"
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2370
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Neudefinition; unterschiedliche Speicherklassen  
  
 Der Bezeichner wurde bereits mit einer anderen Speicherklasse deklariert.  
  
## Beispiel  
 Im folgenden Beispiel wird C2370 generiert:  
  
```  
// C2370.cpp // compile with: /Za /c extern int i; static int i;   // C2370 int i;   // OK  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2370 generiert:  
  
```  
// C2370b.cpp #define Thread __declspec( thread ) extern int tls_i; int Thread tls_i;   // C2370 declaration and the definition differ int tls_i;   // OK  
```