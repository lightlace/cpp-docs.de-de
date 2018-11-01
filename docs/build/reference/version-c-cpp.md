---
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 98758da627390ba4c7e852905457527a343baccc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667375"
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