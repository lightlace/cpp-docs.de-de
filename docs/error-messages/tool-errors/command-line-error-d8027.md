---
title: "Befehlszeilenfehler D8027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D8027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8027"
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Befehlszeilenfehler D8027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Komponente' kann nicht ausgeführt werden  
  
 Die angegebene Compilerkomponente oder der angegebene Linker konnte vom Compiler nicht ausgeführt werden.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es steht nicht genügend Speicher zur Verfügung, um die Komponente zu laden.  Wenn der Compiler durch NMAKE aufgerufen wurde, führen Sie ihn außerhalb eines Makefiles aus.  
  
2.  Die Komponente konnte vom aktuellen Betriebssystem nicht ausgeführt werden.  Stellen Sie sicher, dass der Pfad auf die dem Betriebssystem entsprechenden ausführbaren Dateien zeigt.  
  
3.  Die Komponente war beschädigt.  Kopieren Sie die Komponente von den Programm\-CDs unter Verwendung des Setup\-Programms neu.  
  
4.  Eine Option wurde nicht richtig angegeben.  Beispiel:  
  
    ```  
    cl /B1 file1.c  
    ```