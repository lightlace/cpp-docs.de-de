---
title: Sonderzeichen in Makros
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: aac7b07500d2a129194e7234210a590cb5d0f19a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825450"
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

[Definieren eines NMAKE-Makros](defining-an-nmake-macro.md)
