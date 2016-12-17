---
title: "Compilerwarnung (Stufe 1) C4174"
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
  - "C4174"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4174"
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4174
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Nicht als \#pragma\-Komponente verfügbar.  
  
## Beispiel  
  
```  
// C4174.cpp // compile with: /W1 #pragma component(info)  // C4174; unknown #pragma component(browser, off)  // turn off browse info int main() { }  
```