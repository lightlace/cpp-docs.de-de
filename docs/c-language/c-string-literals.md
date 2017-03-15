---
title: "C-Zeichenfolgenliterale | Microsoft Docs"
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
  - "Literalzeichenfolgen, C"
  - "Zeichenfolgenliterale, Syntax"
  - "Zeichenfolgen [C++], Zeichenfolgenliterale"
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# C-Zeichenfolgenliterale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Zeichenfolgenliteral" ist eine Folge von Zeichen aus dem Quellzeichensatz, umgeben von doppelten Anführungszeichen \(**" "**\).  Zeichenfolgenliterale werden verwendet, um eine Sequenz von Zeichen darzustellen, die zusammen eine auf NULL endende Zeichenfolge bilden.  Sie müssen immer breite Zeichenfolgenliterale mit dem Präfix **L** versehen.  
  
## Syntax  
 *string\-literal*:  
 **"** *s\-char\-sequence*  opt               **"**  
  
 **L"** *s\-char\-sequence*  opt               **"**  
  
 *s\-char\-sequence*:  
 *s\-char*  
  
 *s\-char\-sequence s\-char*  
  
 *s\-char*:  
 alle Member des Quellzeichensatzes mit Ausnahme von doppelten Anführungszeichen \("\), umgekehrtem Schrägstrich \(\\\) oder Zeilenumbruchzeichen  
  
 *escape\-sequence*  
  
 Das unten gezeigte Beispiel ist ein einfaches Zeichenfolgenliteral:  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 Alle Umschaltcodes, die in der [Escapesequenzen](../c-language/escape-sequences.md)\-Tabelle aufgeführt sind, sind gültige Zeichenfolgenliterale.  Um ein doppeltes Anführungszeichen in einem Zeichenfolgenliteral darzustellen, verwenden Sie die Escapesequenz **\\"**.  Das einfache Anführungszeichen \(**'**\) kann ohne Escapesequenz dargestellt werden.  Dem umgekehrten Schrägstrich \(**\\**\) muss ein zweiter umgekehrter Schrägstrich \(**\\\\**\) folgen, wenn er Teil einer Zeichenfolge ist.  Wenn ein umgekehrter Schrägstrich am Ende einer Zeile steht, wird er immer als Zeilenfortsetzungszeichen interpretiert.  
  
## Siehe auch  
 [Elemente von C](../c-language/elements-of-c.md)