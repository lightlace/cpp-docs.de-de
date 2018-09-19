---
title: NAME (C/C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc37a96e50c6cd5bae2cc60661db04f3b92d162b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715753"
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