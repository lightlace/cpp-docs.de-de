---
title: "C-Zeichenkonstanten | Microsoft Docs"
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
  - "(') - einfaches Anführungszeichen"
  - "Zeichen, Konstanten"
  - "Konstanten, Zeichen"
  - "Einfaches Anführungszeichen"
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# C-Zeichenkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Zeichenkonstante" wird gebildet, indem ein einzelnes Zeichen aus dem darstellbaren Zeichensatz in einfache Anführungszeichen \(**' '**\) eingeschlossen wird.  Zeichenkonstanten werden verwendet, um Zeichen im [Ausführungszeichensatz](../c-language/execution-character-set.md) darzustellen.  
  
## Syntax  
 *Zeichenkonstante*:  
 **'** *c\-char\-sequence* **'**  
  
 **L'** *c\-char\-sequence* **'**  
  
 *c\-char\-sequence*:  
 *c\-char*  
  
 *c\-char\-sequence c\-char*  
  
 *c\-char*:  
 Alle Member des Quellzeichensatzes mit Ausnahme von einfachem Anführungszeichen \(**'**\), umgekehrtem Schrägstrich \(**\\**\) oder Zeilenumbruchzeichen  
  
 *escape\-sequence*  
  
 *escape\-sequence*:  
 *simple\-escape\-sequence*  
  
 *octal\-escape\-sequence*  
  
 *hexadecimal\-escape\-sequence*  
  
 *simple\-escape\-sequence*: einer der folgenden Werte  
 **\\a \\b \\f \\n \\r \\t \\v**  
  
 **\\' \\" \\\\ \\?**  
  
 *octal\-escape\-sequence*:  
 **\\**  *octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit octal\-digit*  
  
 *hexadecimal\-escape\-sequence*:  
 **\\x**  *hexadecimal\-digit*  
  
 *hexadecimal\-escape\-sequence hexadecimal\-digit*  
  
## Siehe auch  
 [C\-Konstanten](../c-language/c-constants.md)