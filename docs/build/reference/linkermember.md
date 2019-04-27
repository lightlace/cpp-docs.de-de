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
ms.openlocfilehash: a0456fd9ed1729b4a6cfa200a54ba211a64e94ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216583"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>Hinweise

Diese Option zeigt die öffentlichen Symbole, die in einer Bibliothek definierten. Geben Sie das Argument 1, um Symbole in Objektreihenfolge, zusammen mit ihren Offsets anzuzeigen. Geben Sie das Argument 2, um Offsets und Indexnummern von Objekten anzuzeigen, und führen Sie dann die Symbole in alphabetischer Reihenfolge, zusammen mit dem Objektindex für die einzelnen. Rufen Sie beide Ausgaben angegeben Sie/LINKERMEMBER ohne das Number-Argument werden.

Nur die [/Headers](headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
