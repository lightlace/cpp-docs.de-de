---
title: "Mehrere Inlinedateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinedateien, Mehrfaches NMAKE"
  - "Mehrere Inlinedateien"
  - "NMAKE (Programm), Inlinedateien"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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