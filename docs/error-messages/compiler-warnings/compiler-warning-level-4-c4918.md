---
title: "Compilerwarnung (Stufe 4) C4918 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4918"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4918"
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4918
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'zeichen': Unzulässiges Zeichen in der pragma\-Optimierungsliste  
  
 Ein unbekanntes Zeichen wurde in der Optimierungsliste einer Pragmaanweisung [optimize](../../preprocessor/optimize.md) gefunden.  
  
 Beispielsweise generiert die folgende Anweisung C4918:  
  
```  
// C4918.cpp // compile with: /W4 #pragma optimize("X", on) // C4918 expected int main() { }  
```