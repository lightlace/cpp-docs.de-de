---
title: "Linkertoolfehler LNK1166 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1166"
ms.assetid: d69548a8-0efb-44e1-90b7-b27636a4b575
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK1166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Code kann nicht bei Offset\=Offset, va\=Wert eingestellt werden  
  
 Der Code konnte nicht, wie erforderlich, durch LINK aufgefüllt werden.  
  
 Bei bestimmten Anweisungen ist es auf einigen Prozessoren nicht zulässig, dass die Seitenbegrenzungen überschritten werden.  LINK versucht, Füllzeichen zur Lösung dieses Problems hinzuzufügen.  In diesem Fall konnte das Problem jedoch nicht durch LINK umgangen werden.