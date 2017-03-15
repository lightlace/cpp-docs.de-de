---
title: "ML Nonfatal Error A2133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2133"
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Registriert beim Überschreiben von AUFRUF Wert**  
  
 Ein Register wurde als Argument an eine Prozedur übergeben, aber der Code, der von [AUFRUF](../../assembler/masm/invoke.md) generiert wurde, um weitere Argumente übergeben, zerstörte den Inhalt des Registers.  
  
 Das AX, EAX\-, AH, AL DX\-, DL\-, AVW\-, und EDX\-Register wird vom Assembler verwendet werden, um Datenkonvertierung ausführen.  
  
 Verwenden Sie ein anderes Register.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)