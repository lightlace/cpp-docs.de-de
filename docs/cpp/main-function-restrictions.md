---
title: "Einschr&#228;nkungen der main-Funktion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "Main"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main-Funktion, Einschränkungen bei der Verwendung"
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Einschr&#228;nkungen der main-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für die **main**\-Funktion gelten mehrere Einschränkungen, die auf andere C\+\+\-Funktionen nicht zutreffen.  Die **main**\-Funktion:  
  
-   Kann nicht überladen werden \(siehe [Überladen](../misc/overloading-cpp.md)\).  
  
-   Kann nicht als **inline** deklariert werden.  
  
-   Kann nicht als **statisch** deklariert werden.  
  
-   Ihre Adresse kann nicht übernommen werden.  
  
-   Kann nicht aufgerufen werden.  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)