---
title: "Ausdrucksauswertungsfehler CXX0030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0030"
  - "CXX0030"
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausdruck kann nicht ausgewertet werden  
  
 Es konnte kein Wert für den angegebenen Ausdruck von der Ausdrucksauswertung des Debuggers abgerufen werden.  Möglicherweise wird vom Ausdruck auf Speicher verwiesen, der außerhalb des Speicherbereichs des Programms liegt, z. B. bei der Dereferenzierung eines NULL\-Zeigers.  Unter Windows ist der Zugriff auf Speicher außerhalb des Adressbereichs des Programms nicht zulässig.  
  
 Ein Ausdruck kann neu geschrieben und dabei die Auswertungsreihenfolge mit der Verwendung von Klammern gesteuert werden.  
  
 Dieser Fehler ist mit CAN0030 identisch.