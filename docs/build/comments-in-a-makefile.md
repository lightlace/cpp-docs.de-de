---
title: "Kommentare in einem Makefile | Microsoft Docs"
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
  - "Makefiles, Kommentare"
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Kommentare in einem Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellen Sie Kommentaren ein Nummernzeichen \(**\#**\) voran.  Text nach dem Nummernzeichen wird von NMAKE bis zur nächsten Zeilenendemarke ignoriert.  Beispiele:  
  
```  
# Comment on line by itself  
OPTIONS = /MAP  # Comment on macro definition line  
  
all.exe : one.obj two.obj  # Comment on dependency line  
    link one.obj two.obj  
# Comment in commands block  
#   copy *.obj \objects  # Command turned into comment  
    copy one.exe \release  
  
.obj.exe:  # Comment on inference rule line  
    link $<  
  
my.exe : my.obj ; link my.obj  # Err: cannot comment this  
 # Error: # must be the first character  
.obj.exe: ; link $<  # Error: cannot comment this  
```  
  
 Soll ein literales Nummernzeichen eingegeben werden, muss diesem ein Zirkumflexzeichen \(**^**\) vorangestellt werden:  
  
```  
DEF = ^#define  #Macro for a C preprocessing directive  
```  
  
## Siehe auch  
 [Inhalt eines Makefiles](../build/contents-of-a-makefile.md)