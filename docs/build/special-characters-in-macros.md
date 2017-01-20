---
title: "Sonderzeichen in Makros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sonderzeichen, In NMAKE-Makros"
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Sonderzeichen in Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kommentare werden mit einem Nummernzeichen \(\#\) nach einer Definition angegeben.  Mit dem Zirkumflexzeichen \(**^**\) kann ein literales Nummernzeichen in einem Makro angeben werden \(**^\#**\).  
  
 Mit einem Dollarzeichen \(`$`\) wird ein Makroaufruf angegeben.  Mit **$$** kann ein literales Dollarzeichen \(`$`\) angeben werden.  
  
 Um eine Definition in einer neuen Zeile fortzusetzen, wird die Zeile mit einem umgekehrten Schrägstrich \(**\\**\) beendet.  Sobald das Makro aufgerufen wird, werden der umgekehrte Schrägstrich und die Zeilenendemarke durch ein Leerzeichen ersetzt.  Um einen literalen umgekehrten Schrägstrich am Ende der Zeile einzufügen, wird diesem ein Zirkumflexzeichen \(**^**\) voran\- oder eine Kommentarangabe \(**\#**\) nachgestellt.  
  
 Um eine Zeilenendemarke als Literalzeichen anzugeben, wird die Zeile mit einem Zirkumflexzeichen \(**^**\) beendet:  
  
```  
CMDS = cls^  
dir  
```  
  
## Siehe auch  
 [Definieren eines NMAKE\-Makros](../build/defining-an-nmake-macro.md)