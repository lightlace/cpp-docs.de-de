---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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