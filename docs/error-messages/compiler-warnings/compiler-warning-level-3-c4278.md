---
title: "Compilerwarnung (Stufe 3) C4278"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4278"
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': der Bezeichner in der Typbibliothek 'TLB' ist bereits ein Makro; benutzen Sie den 'rename'\-Qualifizierer  
  
 Bei Verwendung von [\#import](../../preprocessor/hash-import-directive-cpp.md) versucht ein Bezeichner in der zu importierenden Typbibliothek, einen Bezeichner ***Bezeichner*** zu deklarieren.  Dies ist jedoch bereits ein gültiges Symbol.  
  
 Verwenden Sie das `#import` **rename**\-Attribut, um dem Symbol in der Typbibliothek einen Alias zuzuweisen.