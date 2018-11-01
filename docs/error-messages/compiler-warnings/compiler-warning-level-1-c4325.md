---
title: Compilerwarnung (Stufe 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 293cbbcfe134f6cb4f5e1bf924be7c03fa278833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492592"
---
# <a name="compiler-warning-level-1-c4325"></a>Compilerwarnung (Stufe 1) C4325

> Attribute für Standardabschnitt "*Abschnitt*" ignoriert

## <a name="remarks"></a>Hinweise

Sie können die Attribute eines Abschnitts standard nicht ändern. Zum Beispiel:

```cpp
#pragma section(".sdata", long)
```

Dies überschreibt die `.sdata` Abschnitt "standard" verwendet die **kurze** Datentyp mit der **lange** -Datentyp.

Standard-Abschnitten enthalten, deren Attribute, die nicht geändert werden kann,

- ".Data"

- .sdata

- ".BSS"

- .sbss

- .Text

- .const

- .sconst

- .rdata

- .srdata

Zusätzliche Abschnitte ggf. später hinzugefügt werden.

## <a name="see-also"></a>Siehe auch

[section](../../preprocessor/section.md)