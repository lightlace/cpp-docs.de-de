---
title: Linkertoolwarnung LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 0abad1b98ff4782f077312752603ec17fd611c12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390359"
---
# <a name="linker-tools-warning-lnk4197"></a>Linkertoolwarnung LNK4197

> Exportieren von "*Exportname*" angegeben, mehrmals; erste Angabe

Ein Export in mehreren angegeben ist und auf unterschiedliche Weise. Der Linker die erste Spezifikation verwendet und der Rest wird ignoriert.

Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.

Wenn ein Export genau die gleiche Weise mehrere Male angegeben ist, gibt der Linker eine Warnung nicht.

Beispielsweise würde eine DEF-Datei mit folgendem Inhalt, diese Warnung verursachen:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der gleiche Export entspricht sowohl in der Befehlszeile (über Export:) und in der DEF-Datei.

2. Der gleiche Export wird in der DEF-Datei mit unterschiedlichen Attributen zweimal aufgeführt.