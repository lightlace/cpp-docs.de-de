---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c4888b8f9b6dba4b826f2ee7dda7529a4bdf1586
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414498"
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
