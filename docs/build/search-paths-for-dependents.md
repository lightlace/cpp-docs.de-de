---
title: "Suchpfade f&#252;r abh&#228;ngige Dateien"
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
  - "Abhängige Dateien, NMAKE"
  - "NMAKE (Programm), Abhängige Dateien"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Suchpfade f&#252;r abh&#228;ngige Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede abhängige Datei besitzt einen optionalen Suchpfad, der wie folgt angegeben wird:  
  
## Syntax  
  
```  
{directory[;directory...]}dependent  
```  
  
## Hinweise  
 Eine abhängige Datei wird von NMAKE zuerst im aktuellen Verzeichnis und anschließend in Verzeichnissen in der angegebenen Reihenfolge gesucht.  Ein Teil oder der gesamte Suchpfad kann von einem Makro angeben werden.  Verzeichnisnamen werden in geschweiften Klammern \(**{ {** Leerzeichen oder Tabstopps sind nicht zulässig.  
  
## Siehe auch  
 [Abhängige Dateien](../build/dependents.md)