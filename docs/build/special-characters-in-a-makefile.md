---
title: "Sonderzeichen in einem Makefile"
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
  - "Makros, Sonderzeichen"
  - "Makefiles, Sonderzeichen"
  - "NMAKE (Programm), Sonderzeichen"
  - "Sonderzeichen, In NMAKE-Makros"
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Sonderzeichen in einem Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein Sonderzeichen bei NMAKE als ein Literalzeichen einzugeben, wird vor das Sonderzeichen ein Zirkumflexzeichen \(**^**\) gesetzt.  Zirkumflexzeichen vor anderen Zeichen werden von NMAKE ignoriert.  Folgende Sonderzeichen sind vorhanden:  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 Ein Zirkumflexzeichen \(**^**\) innerhalb einer Zeichenfolge in Anführungszeichen wird als literales Zirkumflexzeichen behandelt.  Von Zirkumflexzeichen am Ende einer Zeile wird eine literale Zeilenendemarke in einer Zeichenfolge oder einem Makro eingefügt.  
  
 Bei Makros wird ein umgekehrter Schrägstrich \(**\\**\) vor einer Zeilenendemarke durch ein Leerzeichen ersetzt.  
  
 Bei Befehlen stellt ein Prozentzeichen \(`%`\) den Dateibezeichner dar.  Um dieses Zeichen in einem Befehl als Literalzeichen zu repräsentieren, geben Sie stattdessen ein doppeltes Prozentzeichen \(**%%**\) ein.  Es gibt Situationen, in denen ein einzelnes Prozentzeichen \(`%`\) von NMAKE als Literalzeichen interpretiert wird, ein doppeltes Prozentzeichen \(**%%**\) jedoch immer als einzelnes Prozentzeichen \(`%`\) interpretiert wird.  Soll ein doppeltes literales Prozentzeichen \(**%%**\) repräsentiert werden, werden daher entweder drei Prozentzeichen \(**%%%**\) oder vier Prozentzeichen \(**%%%%**\) eingegeben.  
  
 Um das Dollarzeichen \(`$`\) als Literalzeichen in einem Befehl zu verwenden, werden zwei Dollarzeichen \(**$$**\) eingegeben.  Diese Methode kann auch in Situationen verwendet werden, in denen die **^$**\-Zeichenfolge funktioniert.  
  
## Siehe auch  
 [Inhalt eines Makefiles](../build/contents-of-a-makefile.md)