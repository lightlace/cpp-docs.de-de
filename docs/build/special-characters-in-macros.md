---
title: Sonderzeichen in Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55a94001e2f912049518120911c25ae64afa24da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721423"
---
# <a name="special-characters-in-macros"></a>Sonderzeichen in Makros

Mit einem Nummernzeichen (#), nachdem eine Definition ein Kommentars gibt. Um ein literalen Nummernzeichen in einem Makro anzugeben, verwenden Sie ein Caretzeichen (^), wie in ^ #.

Ein Dollarzeichen ($) wird ein Makroaufruf. Verwenden Sie zum Angeben eines literalen $ $$.

Um eine Definition in eine neue Zeile zu erweitern, beenden Sie die Zeile mit einem umgekehrten Schrägstrich (\\). Wenn das Makro aufgerufen wird, wird das umgekehrten Schrägstrich sowie neue-Zeile-Zeichen durch ein Leerzeichen ersetzt. Um ein literal umgekehrten Schrägstrich am Ende der Zeile ein Caretzeichen (^) voranstellen, oder führen Sie es mit einem Kommentar-Spezifizierer (#).

Beenden Sie die Zeile mit der ein Caretzeichen (^), um ein literal Zeilenumbruchzeichen anzugeben, wie in:

```
CMDS = cls^
dir
```

## <a name="see-also"></a>Siehe auch

[Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)