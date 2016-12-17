---
title: "Compilerfehler C2818"
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
  - "C2818"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2818"
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2818
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Anwendung rekursiven durchgehenden Typs "\>' Typ" \- iss des überladenen Operators '  
  
 Eine Neudefinition des Zugriffsoperators für Klassenmember enthält eine rekursive `return`\-Anweisung.  Um den Operator `->` mit Rekursion neu zu definieren, müssen Sie die rekursive Routine in eine separate Funktion verschieben, die durch die Funktion zum Überschreiben des Operators aufgerufen wird.