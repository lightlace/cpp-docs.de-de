---
title: C-Zeichenkonstanten
ms.date: 11/04/2016
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
ms.openlocfilehash: 5d87b57726f741cc96f2180de33cae01403786ec
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152767"
---
# <a name="c-character-constants"></a>C-Zeichenkonstanten

Eine „Zeichenkonstante“ wird gebildet, indem ein einzelnes Zeichen aus dem darstellbaren Zeichensatz in einfache Anführungszeichen (**' '**) eingeschlossen wird. Zeichenkonstanten werden verwendet, um Zeichen im [Ausführungszeichensatz](../c-language/execution-character-set.md) darzustellen.

## <a name="syntax"></a>Syntax

*character-constant*: **'** *c-char-sequence* **'**

**L'** *c-char-sequence* **'**

*c-char-sequence*: *c-char*

*c-char-sequence c-char*

*c-char*: Alle Elemente des Quellzeichensatzes mit Ausnahme von einfachem Anführungszeichen (**'**), umgekehrtem Schrägstrich (**\\**) oder Zeilenumbruchzeichen

*escape-sequence*

*escape-sequence*: *simple-escape-sequence*

*octal-escape-sequence*

*hexadecimal-escape-sequence*

*simple-escape-sequence*: eines der folgenden Zeichen **\a \b \f \n \r \t \v**

**\\' \\" \\\ \\?**

*octal-escape-sequence*: **\\**  *octal-digit*

**\\** *octal-digit octal-digit*

**\\** *octal-digit octal-digit octal-digit*

*hexadecimal-escape-sequence*: **\x**  *hexadecimal-digit*

*hexadecimal-escape-sequence hexadecimal-digit*

## <a name="see-also"></a>Siehe auch

[C-Konstanten](../c-language/c-constants.md)
