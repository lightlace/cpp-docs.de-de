---
title: Linkertoolwarnung LNK4105 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4411421741cf8bf7c714a6322d58bd177e7e7270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024982"
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