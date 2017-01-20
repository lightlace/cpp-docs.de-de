---
title: "Ressourcencompiler: Schwerwiegender Fehler RW1025"
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
  - "RW1025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1025"
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Schwerwiegender Fehler RW1025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein weiterer Heap\-Speicher vorhanden  
  
 Überprüfen Sie auf speicherresidente Software, die möglicherweise zu viel Speicher in Anspruch nimmt.  Verwenden Sie das CHKDSK\-Programm, um herauszufinden, wie viel Speicher verfügbar ist.  
  
 Wenn Sie eine große Ressourcendatei erstellen, können Sie das Ressourcenskript in zwei Dateien aufteilen.  Verwenden Sie nach dem Erstellen zweier RES\-Dateien die MS\-DOS\-Befehlszeile, um diese zu verknüpfen.  
  
```  
copy first.res /b + second.res /b full.res  
```