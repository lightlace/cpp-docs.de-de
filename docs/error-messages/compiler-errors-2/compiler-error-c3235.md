---
title: "Compilerfehler C3235"
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
  - "C3235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3235"
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Spezialisierung": Die explizite oder teilweise Spezialisierung einer generischen Klasse ist nicht zulässig.  
  
 Generische Klassen können nicht für explizite oder teilweise Spezialisierungen verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3235 generiert.  
  
```  
// C3235.cpp // compile with: /clr generic<class T> public ref class C {}; generic<> public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```