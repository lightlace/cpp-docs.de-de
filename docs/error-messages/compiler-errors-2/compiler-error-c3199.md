---
title: "Compilerfehler C3199 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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