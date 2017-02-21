---
title: "Suchpfade f&#252;r abh&#228;ngige Dateien | Microsoft Docs"
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
  - "Abhängige Dateien, NMAKE"
  - "NMAKE (Programm), Abhängige Dateien"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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