---
title: VERSION (C/C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7330d979e841d952f7e800e52ae762256ede6808
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718301"
---
# <a name="version-cc"></a>VERSION (C/C++)

Gibt LINK zu der eine Zahl im Header der .exe-Datei zu speichern oder DLL an.

```
VERSION major[.minor]
```

## <a name="remarks"></a>Hinweise

Die *wichtigen* und *kleinere* Argumente sind Dezimalzahlen im Bereich von 0 bis 65.535. Der Standardwert ist 0.0.

Alternativ können Sie eine Versionsnummer angeben ist, mit der [Versionsinformationen](../../build/reference/version-version-information.md) (/ VERSION) Option.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)