---
title: Linkertoolwarnung LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 52a4fee532eb9997dcf013f95246b27fdffc4c20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563097"
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