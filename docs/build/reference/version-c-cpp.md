---
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 6d275e1e191e0550143dd5e7a828b734bba0fc96
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414056"
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
