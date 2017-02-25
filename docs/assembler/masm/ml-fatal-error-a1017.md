---
title: "ML Fatal Error A1017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1017"
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**fehlender Quelldateiname**  
  
 ML konnte eine Datei nicht durchsuchen, um zusammenstellen und an den Linker übergeben werden sollen.  
  
 Dieser Fehler wird generiert, wenn Sie ML\-Befehlszeilenoptionen geben, ohne einen Dateinamen angeben zu fungieren.  Um Dateien zusammenzustellen die keine .asm\-Erweiterung haben, verwenden Sie die **\/Ta** Befehlszeilenoption.  
  
 Dieser Fehler kann auch generiert werden, indem ML ohne Parameter aufgerufen wird, wenn die ML\-Umgebungsvariable Befehlszeilenoptionen enthält.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)