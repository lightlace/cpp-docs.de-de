---
title: Werte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bef044535d2f5a5b337823b1798feaea48745d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106273"
---
# <a name="values"></a>Werte

**ANSI 3.1.2.5** Die Darstellungen und Sätze von Werten der verschiedenen Typen von Gleitkommazahlen

Der **float**-Typ enthält 32 Bits: eins für das Zeichen, acht für den Exponenten und 23 für die Mantisse. Sein Bereich ist +/– 3,4E38 mit mindestens 7 Dezimalstellen.

Der **double**-Typ enthält 64 Bits: eins für das Zeichen, elf für den Exponenten und 52 für die Mantisse. Sein Bereich ist +/– 1,7E308 mit mindestens 15 Dezimalstellen.

Der **long double**-Typ enthält 80 Bits: eins für das Zeichen, 15 für den Exponenten und 64 für die Mantisse. Sein Bereich ist +/– 1,2E4932 mit mindestens 19 Dezimalstellen. Beachten Sie, dass mit dem Microsoft C-Compiler die Darstellung des **long double**-Typs mit der des **double**-Typs identisch ist.

## <a name="see-also"></a>Siehe auch

[Gleitkommaoperationen](../c-language/floating-point-math.md)