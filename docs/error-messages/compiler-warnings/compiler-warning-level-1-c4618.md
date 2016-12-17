---
title: "Compilerwarnung (Stufe 1) C4618"
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
  - "C4618"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4618"
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4618
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragma\-Parameter enthalten eine leere Zeichenfolge; Pragma wird ignoriert  
  
 Einem **\#pragma** wurde als Argument eine NULL\-Zeichenfolge übergeben.  
  
 Das Pragma wurde ohne das Argument verarbeitet.  
  
 Im folgenden Beispiel wird C4618 generiert:  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```