---
title: Zeichenfolgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cf3b52b8a4e76062d06b0b9ca3d4535b79595c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061512"
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