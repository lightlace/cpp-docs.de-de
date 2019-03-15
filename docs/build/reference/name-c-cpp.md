---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: d0813befc622db72e095c449794405fc5d58465b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812186"
---
# <a name="name-cc"></a>NAME (C/C++)

Gibt einen Namen für die main-Ausgabedatei.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Hinweise

Alternativ können Sie einen Ausgabedateinamen angeben ist, mit der [/OUT](out-output-file-name.md) -Linkeroption, und eine entsprechende Methode zum Festlegen der Basisadresse wird mit der [/BASE](base-base-address.md) (Linkeroption). Wenn beide angegeben sind "," / OUT überschreibt **Namen**.

Wenn Sie eine DLL-Datei erstellen, wirkt sich NAME nur den Namen der DLL.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)
