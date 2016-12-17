---
title: "Ausdrucksauswertungsfehler CXX0065"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0065"
  - "CXX0065"
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ausdrucksauswertungsfehler CXX0065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Variable erfordert Stapelrahmen  
  
 Ein Ausdruck enthält eine Variable, die im aktuellen Gültigkeitsbereich vorhanden ist, jedoch noch nicht erstellt wurde.  
  
 Dieser Fehler kann auftreten, wenn der Prolog einer Funktion schrittweise ausgeführt wird, der Stapelrahmen aber noch nicht eingerichtet wurde, oder wenn der Exitcode schrittweise ausgeführt wird.  
  
 Der Prolog muss so lange schrittweise ausgeführt werden, bis der Stapelrahmen eingerichtet ist, bevor der Ausdruck ausgewertet wird.  
  
 Dieser Fehler ist mit CAN0065 identisch.