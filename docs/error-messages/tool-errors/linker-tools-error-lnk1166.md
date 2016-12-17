---
title: "Linkertoolfehler LNK1166"
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
  - "LNK1166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1166"
ms.assetid: d69548a8-0efb-44e1-90b7-b27636a4b575
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Code kann nicht bei Offset\=Offset, va\=Wert eingestellt werden  
  
 Der Code konnte nicht, wie erforderlich, durch LINK aufgefüllt werden.  
  
 Bei bestimmten Anweisungen ist es auf einigen Prozessoren nicht zulässig, dass die Seitenbegrenzungen überschritten werden.  LINK versucht, Füllzeichen zur Lösung dieses Problems hinzuzufügen.  In diesem Fall konnte das Problem jedoch nicht durch LINK umgangen werden.