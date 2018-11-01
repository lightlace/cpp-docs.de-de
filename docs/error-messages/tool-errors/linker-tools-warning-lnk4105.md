---
title: Linkertoolwarnung LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 880c8519a530f492d0c322575a1386af8a7d0187
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475590"
---
# <a name="linker-tools-warning-lnk4105"></a>Linkertoolwarnung LNK4105

kein Argument angegeben mit der Option 'Option'; Option wird ignoriert.

Diese Warnung tritt nur auf, wenn die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option festgelegt ist. Wenn kein Verzeichnis mit dieser Option angegeben wird, klicken Sie dann der Linker ignoriert die Option, und diese Warnmeldung generiert.

Wenn Sie nicht die vorhandenen umgebungsbibliothekspfads Einstellungen außer Kraft setzen müssen, entfernen Sie die/LIBPATH-Option von der Befehlszeile des Linkers. Wenn Sie einen alternativen Suchpfad für Bibliotheken verwenden möchten, geben Sie den alternativen Pfad nach der Option/LIBPATH.

## <a name="example"></a>Beispiel

```
link /libpath:c:\filepath\lib bar.obj
```

leitet den Linker an, die erforderlichen Bibliotheken im suchenden `c:\filepath\lib` vor in den Standardverzeichnissen.