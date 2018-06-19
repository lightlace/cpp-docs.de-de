---
title: C-Zeichenkonstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0009f795936da7eb0c2ff69aa192e8f609638d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382285"
---
# <a name="c-character-constants"></a>C-Zeichenkonstanten
Eine „Zeichenkonstante“ wird gebildet, indem ein einzelnes Zeichen aus dem darstellbaren Zeichensatz in einfache Anführungszeichen (**' '**) eingeschlossen wird. Zeichenkonstanten werden verwendet, um Zeichen im [Ausführungszeichensatz](../c-language/execution-character-set.md) darzustellen.  
  
## <a name="syntax"></a>Syntax  
 *character-constant*:  
 **'** *c-char-sequence* **'**  
  
 **L'** *c-char-sequence* **'**  
  
 *c-char-sequence*:  
 *c-char*  
  
 *c-char-sequence c-char*  
  
 *c-char*:  
 Alle Elemente des Quellzeichensatzes mit Ausnahme von einfachem Anführungszeichen (**'**), umgekehrtem Schrägstrich (**\\**) oder Zeilenumbruchzeichen  
  
 *escape-sequence*  
  
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
 [C-Konstanten](../c-language/c-constants.md)