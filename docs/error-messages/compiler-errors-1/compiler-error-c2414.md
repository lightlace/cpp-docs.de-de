---
title: "Compilerfehler C2414 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2414"
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Operandenanzahl  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht.  Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.  
  
2.  Neuere Prozessoren unterstützen die Anweisung mit einer unterschiedlichen Anzahl von Operanden.  Passen Sie die Option [\/arch \(Minimale CPU\-Architektur\)](../../build/reference/arch-minimum-cpu-architecture.md) an, um den neueren Prozessor zu verwenden.