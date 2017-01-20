---
title: "ML Nonfatal Error A2133"
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
  - "A2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2133"
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Registriert beim Überschreiben von AUFRUF Wert**  
  
 Ein Register wurde als Argument an eine Prozedur übergeben, aber der Code, der von [AUFRUF](../../assembler/masm/invoke.md) generiert wurde, um weitere Argumente übergeben, zerstörte den Inhalt des Registers.  
  
 Das AX, EAX\-, AH, AL DX\-, DL\-, AVW\-, und EDX\-Register wird vom Assembler verwendet werden, um Datenkonvertierung ausführen.  
  
 Verwenden Sie ein anderes Register.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)