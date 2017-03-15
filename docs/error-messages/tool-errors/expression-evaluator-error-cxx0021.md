---
title: "Ausdrucksauswertungsfehler CXX0021 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0021"
  - "CXX0021"
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

struct oder union als Skalarwert verwendet  
  
 Eine Struktur oder Union wurde in einem Ausdruck verwendet. Es wurde jedoch kein Element angegeben.  
  
 Wenn eine Struktur\- oder Unionvariable geändert wird, sollte der Name der Variablen ohne einen Feldqualifizierer angegeben werden.  Wenn eine Struktur oder Union in einem Ausdruck verwendet wird, muss sie durch ein bestimmtes Element gekennzeichnet werden.  
  
 Geben Sie das Element an, dessen Wert in dem Ausdruck verwendet werden soll.  
  
 Dieser Fehler ist mit CAN0021 identisch.