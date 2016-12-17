---
title: "Zusammenfassung der Konstanten"
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
  - "C"
helpviewer_keywords: 
  - "Konstanten, C"
ms.assetid: 4158234c-e189-4e25-970f-52a04bc6380a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Zusammenfassung der Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`constant`:  
 *floating\-point\-constant*  
  
 *integer\-constant*  
  
 *enumeration\-constant*  
  
 *character\-constant*  
  
 *floating\-point\-constant*:  
 *fractional\-constant exponent\-part*  opt *floating\-suffix* opt  
  
 *digit\-sequence exponent\-part floating\-suffix*  opt  
  
 *fractional\-constant*:  
 *digit\-sequence*  opt **.***digit\-sequence*  
  
 *digit\-sequence*  **.**  
  
 *exponent\-part*:  
 **e**  *sign*  opt *digit\-sequence*  
  
 **E**  *sign*  opt *digit\-sequence*  
  
 *Vorzeichen*: eins der Folgenden  
 **\+ –**  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence\-Stelle*  
  
 *floating\-suffix*: eins der Folgenden  
 **f l F L**  
  
 *integer\-constant*:  
 *decimal\-constant integer\-suffix*  opt  
  
 *octal\-constant integer\-suffix*  opt  
  
 *hexadecimal\-constant integer\-suffix*  opt  
  
 *decimal\-constant*:  
 *nonzero\-digit*  
  
 *decimal\-constant digit*  
  
 *octal\-constant*:  
 **0**  
  
 *octal\-constant octal\-digit*  
  
 *hexadecimal\-constant*:  
 **0x**  *hexadecimal\-digit*  
  
 **0X**  *hexadecimal\-digit*  
  
 *hexadecimal\-constant hexadecimal\-digit*  
  
 *nonzero\-digit*: one of  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal\-digit*: one of  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal\-digit*: one of  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *unsigned\-suffix*: one of  
 **u U**  
  
 *long\-suffix*: one of  
 **l L**  
  
 *Zeichenkonstante*:  
 **'** *c\-char\-sequence*  
  
 **'L'** *c\-char\-sequence* **'**  
  
 *integer\-suffix*:  
 *unsigned\-suffix long\-suffix*  opt  
  
 *long\-suffix unsigned\-suffix*  opt  
  
 *c\-char\-sequence*:  
 *c\-char*  
  
 *c\-char\-sequence c\-char*  
  
 *c\-char*:  
 Alle Member des Quellzeichensatzes mit Ausnahme von einfachem Anführungszeichen \('\), umgekehrtem Schrägstrich \(**\\**\) oder Zeilenumbruchzeichen *Escapesequenz*  
  
 *escape\-sequence*:  
 *simple\-escape\-sequence*  
  
 *octal\-escape\-sequence*  
  
 *hexadecimal\-escape\-sequence*  
  
 *simple\-escape\-sequence*: einer der folgenden Werte  
 **\\a \\b \\f \\n \\r \\t \\v**  
  
 **\\' \\" \\\\ \\?**  
  
 *octal\-escape\-sequence*:  
 **\\** *octal\-digit*  
  
 **\\** *octal\-digit octal\-digit*  
  
 **\\** *octal\-digit octal\-digit octal\-digit*  
  
 *hexadecimal\-escape\-sequence*:  
 **\\x**  *hexadecimal\-digit*  
  
 *hexadecimal\-escape\-sequence hexadecimal\-digit*  
  
## Siehe auch  
 [Lexikalische Grammatik](../c-language/lexical-grammar.md)