---
title: "ML Nonfatal Error A2050"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**echte oder BCD\-Zahl nicht zulässig**  
  
 Eine Gleitkommazahl \(realen\) Konstante der Zahl oder binär verschlüsselten BCD \(dezimal\) folgte anders als Bezugspunkt initialisierer verwendet.  
  
 Eines der folgenden Schritte ausgeführt:  
  
-   Eine reelle Zahl oder eine BCD wurden in einem Ausdruck verwendet wird.  
  
-   Eine reelle Zahl wurde verwendet, um Direktive außer [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md)oder [TBYTE](../../assembler/masm/tbyte.md)zu initialisieren.  
  
-   Ein BCD wurde verwendet, um Direktive außer `TBYTE`zu initialisieren.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)