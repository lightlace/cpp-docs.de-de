---
title: Zeichensequenzen
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: dea24a2ae5887ea8c0111d8251ba4d9d03ccba0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489660"
---
# <a name="character-sequences"></a>Zeichensequenzen

**ANSI 3.8.2** Die Zuordnung der Quelldatei-Zeichenfolgen

Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden.

Um einen Pfad für eine Includedatei anzugeben, verwenden Sie nur einen umgekehrten Schrägstrich:

```
#include "path1\path2\myfile"
```

Im Quellcode sind zwei umgekehrte Schrägstriche erforderlich:

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>Siehe auch

[Präprozessoranweisungen](../c-language/preprocessing-directives.md)