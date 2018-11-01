---
title: C-Zeichenfolgenliterale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/31/2018
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
ms.openlocfilehash: 6101c45f30284633c5f10c148be5a15e1e81dde7
ms.sourcegitcommit: f9d9db80a8f13eae2c41337b974e1298109e33c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "49640730"
---
# <a name="c-string-literals"></a>C-Zeichenfolgenliterale

Ein „Zeichenfolgenliteral“ ist eine Folge von Zeichen aus dem Quellzeichensatz, umgeben von doppelten Anführungszeichen (**" "**). Zeichenfolgenliterale werden verwendet, um eine Sequenz von Zeichen darzustellen, die zusammen eine auf NULL endende Zeichenfolge bilden. Sie müssen immer breite Zeichenfolgenliterale mit dem Präfix **L** versehen.

## <a name="syntax"></a>Syntax

*string-literal*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *s-char-sequence*<sub>opt</sub> **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L"** *s-char-sequence*<sub>opt</sub> **"**

*s-char-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char*

&nbsp;&nbsp;&nbsp;&nbsp;*s-char-sequence* *s-char*

*s-char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;alle Elemente des Quellzeichensatzes mit Ausnahme von doppelten Anführungszeichen ("), umgekehrtem Schrägstrich (\\) oder Zeilenumbruchzeichen<br/>

&nbsp;&nbsp;&nbsp;&nbsp;*escape-sequence*

## <a name="remarks"></a>Hinweise

Das unten gezeigte Beispiel ist ein einfaches Zeichenfolgenliteral:

```C
char *amessage = "This is a string literal.";
```

Alle Umschaltcodes, die in der Tabelle [Escapesequenzen](../c-language/escape-sequences.md) aufgeführt sind, sind gültige Zeichenfolgenliterale. Um ein doppeltes Anführungszeichen in einem Zeichenfolgenliteral darzustellen, verwenden Sie die Escapesequenz **\\"**. Das einfache Anführungszeichen (**'**) kann ohne Escapesequenz dargestellt werden. Dem umgekehrten Schrägstrich (**\\**) muss ein zweiter umgekehrter Schrägstrich (**\\\\**) folgen, wenn er Teil einer Zeichenfolge ist. Wenn ein umgekehrter Schrägstrich am Ende einer Zeile steht, wird er immer als Zeilenfortsetzungszeichen interpretiert.

## <a name="see-also"></a>Siehe auch

[C-Elemente](../c-language/elements-of-c.md)
