---
title: "Compilerfehler C2312"
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
  - "C2312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2312"
ms.assetid: c8bcfd06-12c1-4323-bb53-ba392d36daa4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ausnahme1": wurde aufgefangen durch "Ausnahme2" in Zeilennummer  
  
 Derselbe Ausnahmetyp wird durch zwei Handler aufgefangen.  
  
 Im folgenden Beispiel wird C2312 generiert:  
  
```  
// C2312.cpp // compile with: /EHsc #include <eh.h> int main() { try { throw "ooops!"; } catch( signed int ) {} catch( int ) {}   // C2312 }  
```