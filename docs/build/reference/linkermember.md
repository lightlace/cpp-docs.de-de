---
title: -LINKERMEMBER | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /linkermember
dev_langs:
- C++
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0979009260381eb210e7992377bab8b5ae613338
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700608"
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