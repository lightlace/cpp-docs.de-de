---
title: TMP_MAX, L_tmpnam
ms.date: 11/04/2016
f1_keywords:
- TMP_MAX
- L_tmpnam
helpviewer_keywords:
- temporary files, length
- L_tmpnam constant
- TMP_MAX constant
ms.assetid: ab19fd0c-b5b7-49f7-b23d-da9dfbcf0c1f
ms.openlocfilehash: 21b56a05b60067e04d0d3864a135ed5eccacfddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609715"
---
# <a name="tmpmax-ltmpnam"></a>TMP_MAX, L_tmpnam

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

`TMP_MAX` ist die maximale Anzahl von eindeutigen Dateinamen, die die `tmpnam`-Funktion generieren kann. `L_tmpnam` ist die Länge temporärer Dateinamen, die von `tmpnam` generiert werden.

## <a name="see-also"></a>Siehe auch

[Globale Konstanten](../c-runtime-library/global-constants.md)