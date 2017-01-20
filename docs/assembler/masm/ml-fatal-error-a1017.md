---
title: "ML Fatal Error A1017"
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
  - "A1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1017"
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**fehlender Quelldateiname**  
  
 ML konnte eine Datei nicht durchsuchen, um zusammenstellen und an den Linker übergeben werden sollen.  
  
 Dieser Fehler wird generiert, wenn Sie ML\-Befehlszeilenoptionen geben, ohne einen Dateinamen angeben zu fungieren.  Um Dateien zusammenzustellen die keine .asm\-Erweiterung haben, verwenden Sie die **\/Ta** Befehlszeilenoption.  
  
 Dieser Fehler kann auch generiert werden, indem ML ohne Parameter aufgerufen wird, wenn die ML\-Umgebungsvariable Befehlszeilenoptionen enthält.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)