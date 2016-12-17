---
title: "Linkertoolwarnung LNK4001"
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
  - "LNK4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4001"
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Keine Objektdateien angegeben; Bibliotheken werden verwendet  
  
 An den Linker wurden eine oder mehrere LIB\-Dateien, aber keine OBJ\-Dateien übergeben.  
  
 Da der Linker nicht in der Lage ist, in einer LIB\-Datei auf dieselben Informationen zuzugreifen wie in einer OBJ\-Datei, weist diese Warnung darauf hin, dass Sie explizit andere Linkeroptionen angeben müssen.  Unter Umständen müssen Sie z. B. die Optionen [\/MACHINE](../../build/reference/machine-specify-target-platform.md), [\/OUT](../../build/reference/out-output-file-name.md) oder [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) angeben.