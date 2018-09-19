---
title: Linkertoolwarnung LNK4222 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abc4f85fbc361b37d9325f9d395a1c34e1eeed2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106926"
---
# <a name="linker-tools-warning-lnk4222"></a>Linkertoolwarnung LNK4222

dem exportierten Symbol 'Symbol' sollte keine Ordinalzahl zugewiesen werden

Die folgenden Symbole sollen nach Ordnungszahl nicht exportiert werden:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Diese Funktionen befinden sich immer den Namen mithilfe von `GetProcAddress`. Der Linker warnt vor dieser Art der Export ist, da es zu vergrößern führen kann. Dies kann passieren, wenn der Bereich Ihrer ordinal Exporte mit relativ wenigen Exporten groß ist. Ein auf ein Objekt angewendeter

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

ist erforderlich, dass die slots von 100 in der Exporttabelle der Adresse 98 davon nur Filler (2-99). Auf der anderen Seite

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

Sie benötigen zwei Slots. (Beachten Sie, dass Sie auch exportieren können, mit der [/EXPORT](../../build/reference/export-exports-a-function.md) -Linkeroption.)