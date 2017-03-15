---
title: "Ausdrucksauswertungsfehler CXX0039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0039"
  - "CXX0039"
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Symbol ist mehrdeutig  
  
 Es kann von der C\-Ausdrucksauswertung nicht bestimmt werden, welche Instanz eines Symbols in einem Ausdruck verwendet wird.  Das Symbol tritt mehr als einmal in der Vererbungsstruktur auf.  
  
 Um explizit die Instanz anzugeben, die in diesem Ausdruck verwendet werden soll, muss der Bereichsoperator \(`::`\) verwendet werden.  
  
 Dieser Fehler ist mit CAN0039 identisch.