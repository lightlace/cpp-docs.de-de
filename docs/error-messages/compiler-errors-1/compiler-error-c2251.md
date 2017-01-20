---
title: "Compilerfehler C2251"
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
  - "C2251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2251"
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Namespace 'Namespace' besitzt keinen Member 'Member'. Haben Sie 'Member' gemeint?  
  
 Der Compiler konnte einen Bezeichner nicht im angegebenen Namespace finden.  
  
 Im folgenden Beispiel wird C2251 generiert:  
  
```  
// C2251.cpp // compile with: /c namespace A { namespace B { void f1(); } using namespace B; } void A::f1() {}   // C2251 void A::B::f1() {}   // OK  
```