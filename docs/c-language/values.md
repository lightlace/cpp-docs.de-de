---
title: Werte
ms.date: 11/04/2016
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
ms.openlocfilehash: e0a200bfea8c0a0a06f064b280dad320da25550c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534055"
---
# <a name="values"></a>Werte

**ANSI 3.1.2.5** Die Darstellungen und Sätze von Werten der verschiedenen Typen von Gleitkommazahlen

Der **float**-Typ enthält 32 Bits: eins für das Zeichen, acht für den Exponenten und 23 für die Mantisse. Sein Bereich ist +/– 3,4E38 mit mindestens 7 Dezimalstellen.

Der **double**-Typ enthält 64 Bits: eins für das Zeichen, elf für den Exponenten und 52 für die Mantisse. Sein Bereich ist +/– 1,7E308 mit mindestens 15 Dezimalstellen.

Der **long double**-Typ enthält 80 Bits: eins für das Zeichen, 15 für den Exponenten und 64 für die Mantisse. Sein Bereich ist +/– 1,2E4932 mit mindestens 19 Dezimalstellen. Beachten Sie, dass mit dem Microsoft C-Compiler die Darstellung des **long double**-Typs mit der des **double**-Typs identisch ist.

## <a name="see-also"></a>Siehe auch

[Gleitkommaoperationen](../c-language/floating-point-math.md)