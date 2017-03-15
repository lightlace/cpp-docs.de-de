---
title: "Definieren einer Regel | Microsoft Docs"
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
  - "Definieren von Rückschlussregeln"
  - "NMAKE (Programm), Rückschlussregeln"
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Definieren einer Regel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*fromext* repräsentiert die Erweiterung einer abhängigen Datei, *toext* repräsentiert die Erweiterung der Zieldatei.  
  
```  
.fromext.toext:  
   commands  
```  
  
## Hinweise  
 Bei Erweiterungen wird die Groß\-\/Kleinschreibung nicht beachtet.  Makros können aufgerufen werden, um *fromext* und *toext* zu repräsentieren. Diese werden während des Präprozessorlaufs erweitert.  Der Punkt \(.\) vor *fromext* muss am Zeilenanfang stehen.  Dem Doppelpunkt \(:\) können Leerzeichen oder Tabstopps in beliebiger Anzahl vorangestellt sein.  Nach dem Doppelpunkt dürfen sich nur Leerzeichen oder Tabstopps, ein Semikolon \(;\) für die Angabe eines Befehls, ein Nummernzeichen \(\#\) für Kommentare oder eine Zeilenendemarke befinden.  Andere Leerzeichen sind nicht zulässig.  Befehle werden wie in Beschreibungsblöcken angegeben.  
  
## Worüber möchten Sie mehr erfahren?  
 [Suchpfade in Regeln](../build/search-paths-in-rules.md)  
  
## Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)