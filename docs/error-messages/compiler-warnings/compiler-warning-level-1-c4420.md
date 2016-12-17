---
title: "Compilerwarnung (Stufe 1) C4420"
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
  - "C4420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4420"
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Operator nicht verfügbar; 'Operator' wird stattdessen verwendet; die Laufzeitprüfung ist möglicherweise gefährdet  
  
 Diese Warnung wird erzeugt, wenn Sie die [\/RTCv](../../build/reference/rtc-run-time-error-checks.md)\-Option \(new\/delete\-Vektor prüfen\) verwenden und keine Vektorform gefunden wurde.  In diesem Fall wird die Nicht\-Vektorform verwendet.  
  
 Damit \/RTCv ordnungsgemäß funktioniert, sollte der Compiler immer die Vektorform von [new](../../cpp/new-operator-cpp.md)\/[delete](../../cpp/delete-operator-cpp.md) aufrufen, falls die Vektorsyntax verwendet wurde.