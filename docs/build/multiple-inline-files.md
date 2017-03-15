---
title: "Mehrere Inlinedateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinedateien, Mehrfaches NMAKE"
  - "Mehrere Inlinedateien"
  - "NMAKE (Programm), Inlinedateien"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Mehrere Inlinedateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mehrere Inlinedateien können von einem Befehl erstellt werden.  
  
## Syntax  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## Hinweise  
 Für jede Datei wird eine oder mehrere Zeilen mit Inlinetext vor einer abschließenden Zeile mit dem Trennzeichen eingegeben.  Der Text der zweiten Datei wird in der Zeile begonnen, die auf die Trennzeile für die erste Datei folgt.  
  
## Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)