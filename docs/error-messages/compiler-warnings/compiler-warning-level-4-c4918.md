---
title: "Compilerwarnung (Stufe 4) C4918"
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
  - "C4918"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4918"
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4918
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'zeichen': Unzulässiges Zeichen in der pragma\-Optimierungsliste  
  
 Ein unbekanntes Zeichen wurde in der Optimierungsliste einer Pragmaanweisung [optimize](../../preprocessor/optimize.md) gefunden.  
  
 Beispielsweise generiert die folgende Anweisung C4918:  
  
```  
// C4918.cpp // compile with: /W4 #pragma optimize("X", on) // C4918 expected int main() { }  
```