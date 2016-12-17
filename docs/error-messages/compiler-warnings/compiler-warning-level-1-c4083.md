---
title: "Compilerwarnung (Stufe 1) C4083"
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
  - "C4083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4083"
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Token' erwartet; Bezeichner 'Bezeichner' gefunden  
  
 Ein Bezeichner wurde in einer **\#pragma**\-Anweisung an der falschen Stelle angegeben.  
  
## Beispiel  
  
```  
// C4083.cpp  
// compile with: /W1 /LD  
#pragma warning disable:4083    // C4083  
#pragma warning(disable:4083)   //correct  
```  
  
 Überprüfen Sie die Syntax der [\#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)\-Direktiven.