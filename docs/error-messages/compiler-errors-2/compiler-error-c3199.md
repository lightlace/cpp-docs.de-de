---
title: "Compilerfehler C3199"
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
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Verwendung von Gleitkomma\-Pragmas: Ausnahmen werden nur im präzisen Modus unterstützt  
  
 Das [float\_control](../../preprocessor/float-control.md)\-Pragma wurde verwendet, um ein Gleitkomma\-Ausnahmemodell unter einer [\/fp](../../build/reference/fp-specify-floating-point-behavior.md)\-Einstellung anders als **\/fp:precise** festzulegen.  
  
 Im folgenden Beispiel wird C3199 generiert:  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```