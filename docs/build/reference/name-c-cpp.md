---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c05e82409d6b6e48390d54160e8ff23ada788d41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646198"
---
# <a name="name-cc"></a>NAME (C/C++)

Gibt einen Namen für die main-Ausgabedatei.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Hinweise

Alternativ können Sie einen Ausgabedateinamen angeben ist, mit der [/OUT](../../build/reference/out-output-file-name.md) -Linkeroption, und eine entsprechende Methode zum Festlegen der Basisadresse wird mit der [/BASE](../../build/reference/base-base-address.md) (Linkeroption). Wenn beide angegeben sind "," / OUT überschreibt **Namen**.

Wenn Sie eine DLL-Datei erstellen, wirkt sich NAME nur den Namen der DLL.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)