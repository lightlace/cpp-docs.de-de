---
title: Compilerwarnung (Stufe 1) C4325 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd265938afb51cc402dc84f38b7e95188c6292a7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197484"
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