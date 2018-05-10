---
title: C-Zeichenfolgenliterale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 303ad83c5e366f32a99a501a58b168ef25adbb42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="c-string-literals"></a>C-Zeichenfolgenliterale
Ein „Zeichenfolgenliteral“ ist eine Folge von Zeichen aus dem Quellzeichensatz, umgeben von doppelten Anführungszeichen (**" "**). Zeichenfolgenliterale werden verwendet, um eine Sequenz von Zeichen darzustellen, die zusammen eine auf NULL endende Zeichenfolge bilden. Sie müssen immer breite Zeichenfolgenliterale mit dem Präfix **L** versehen.  
  
## <a name="syntax"></a>Syntax  
 *string-literal*:  
 **"** *s-char-sequence* opt **"**  
  
 **L"** *s-char-sequence* opt **"**  
  
 *s-char-sequence*:  
 *s-char*  
  
 *s-char-sequence s-char*  
  
 *s-char*:  
 alle Elemente des Quellzeichensatzes mit Ausnahme von doppelten Anführungszeichen ("), umgekehrtem Schrägstrich (\\) oder Zeilenumbruchzeichen  
  
 *escape-sequence*  
  
 Das unten gezeigte Beispiel ist ein einfaches Zeichenfolgenliteral:  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 Alle Umschaltcodes, die in der Tabelle [Escapesequenzen](../c-language/escape-sequences.md) aufgeführt sind, sind gültige Zeichenfolgenliterale. Um ein doppeltes Anführungszeichen in einem Zeichenfolgenliteral darzustellen, verwenden Sie die Escapesequenz **\\"**. Das einfache Anführungszeichen (**'**) kann ohne Escapesequenz dargestellt werden. Dem umgekehrten Schrägstrich (**\\**) muss ein zweiter umgekehrter Schrägstrich (**\\\\**) folgen, wenn er Teil einer Zeichenfolge ist. Wenn ein umgekehrter Schrägstrich am Ende einer Zeile steht, wird er immer als Zeilenfortsetzungszeichen interpretiert.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Elemente](../c-language/elements-of-c.md)