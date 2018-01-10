---
title: Zusammenfassung der Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: constants, C
ms.assetid: 4158234c-e189-4e25-970f-52a04bc6380a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e46966d56084a615ffdf2763adefbcd1e416a6ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="summary-of-constants"></a>Zusammenfassung der Konstanten
`constant`:  
 *floating-point-constant*  
  
 *integer-constant*  
  
 *enumeration-constant*  
  
 *character-constant*  
  
 *floating-point-constant*:  
 *fractional-constant exponent-part*-Opt *floating-suffix*-Opt  
  
 *digit-sequence exponent-part floating-suffix*-Opt  
  
 *fractional-constant*:  
 *digit-sequence*-Opt**.***digit-sequence*  
  
 *digit-sequence* **.**  
  
 *exponent-part*:  
 **e** *sign*-Opt*digit-sequence*  
  
 **E** *sign*-Opt*digit-sequence*  
  
 *sign*: eins der folgenden Zeichen  
 **+ -**  
  
 *digit-sequence*:  
 *digit*  
  
 *digit-sequence digit*  
  
 *floating-suffix* : eins der folgenden Zeichen  
 **f l F L**  
  
 *integer-constant*:  
 *decimal-constant integer-suffix*-Opt  
  
 *octal-constant integer-suffix*-Opt  
  
 *hexadecimal-constant integer-suffix*-Opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x** *hexadecimal-digit*  
  
 **0X** *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: eines der folgenden Zeichen  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: eines der folgenden Zeichen  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: eines der folgenden Zeichen  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *unsigned-suffix*: eins der folgenden Zeichen  
 **u U**  
  
 *long-suffix*: eines der folgenden Zeichen  
 **l L**  
  
 *character-constant*:  
 **'** *c-char-sequence*  
  
 **'L'** *c-char-sequence* **'**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix*-Opt  
  
 *long-suffix unsigned-suffix*-Opt  
  
 *c-char-sequence*:  
 *c-char*  
  
 *c-char-sequence c-char*  
  
 *c-char*:  
 Alle Member des Quellzeichensatzes mit Ausnahme von einfachem Anführungszeichen ('), umgekehrtem Schrägstrich (**\\**) oder Zeilenumbruchzeichen *escape-sequence*  
  
 *escape-sequence*:  
 *simple-escape-sequence*  
  
 *octal-escape-sequence*  
  
 *hexadecimal-escape-sequence*  
  
 *simple-escape-sequence*: eins der folgenden Zeichen  
 **\a \b \f \n \r \t \v**  
  
 **\\' \\" \\\ \\?**  
  
 *octal-escape-sequence*:  
 **\\** *octal-digit*  
  
 **\\** *octal-digit octal-digit*  
  
 **\\** *octal-digit octal-digit octal-digit*  
  
 *hexadecimal-escape-sequence*:  
 **\x** *hexadecimal-digit*  
  
 *hexadecimal-escape-sequence hexadecimal-digit*  
  
## <a name="see-also"></a>Siehe auch  
 [Lexikalische Grammatik](../c-language/lexical-grammar.md)