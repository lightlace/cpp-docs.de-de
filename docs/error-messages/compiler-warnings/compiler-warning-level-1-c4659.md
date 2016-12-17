---
title: "Compilerwarnung (Stufe 1) C4659"
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
  - "C4659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4659"
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'Pragma': Verwendung des reservierten Segments 'Segment' hat ein undefiniertes Verhalten. Verwenden Sie \#pragma comment\(linker, ...\)  
  
 Die .drectve\-Option wurde zur Übergabe einer Option an den Linker verwendet.  Verwenden Sie zur Übergabe einer Linkeroption stattdessen pragma [comment](../../preprocessor/comment-c-cpp.md).  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```