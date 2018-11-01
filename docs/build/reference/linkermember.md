---
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: e55f613566b5c3bd7709fe7f30cd0ae985cd369f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494439"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>Hinweise

Diese Option zeigt die öffentlichen Symbole, die in einer Bibliothek definierten. Geben Sie das Argument 1, um Symbole in Objektreihenfolge, zusammen mit ihren Offsets anzuzeigen. Geben Sie das Argument 2, um Offsets und Indexnummern von Objekten anzuzeigen, und führen Sie dann die Symbole in alphabetischer Reihenfolge, zusammen mit dem Objektindex für die einzelnen. Rufen Sie beide Ausgaben angegeben Sie/LINKERMEMBER ohne das Number-Argument werden.

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)