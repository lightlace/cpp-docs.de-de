---
title: "Compilerfehler C2415 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2415"
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2415
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Operandentyp  
  
 Der Opcode verwendet keine Operanden dieses Typs.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht.  Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.  
  
2.  Neuere Prozessoren unterstützen die Anweisung durch zusätzliche Typen.  Passen Sie die Option [\/arch \(Minimale CPU\-Architektur\)](../../build/reference/arch-minimum-cpu-architecture.md) an, um den neueren Prozessor zu verwenden.