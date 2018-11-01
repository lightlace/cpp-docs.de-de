---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: de2aa99375f588d682b714632590ba8e0db8ddcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597222"
---
# <a name="stacksize"></a>STACKSIZE

Legt die Stapelgröße in Bytes fest.

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Hinweise

Alternativ können Sie den Stapel festgelegt ist, mit der [Stapelreservierungen](../../build/reference/stack-stack-allocations.md) (/ STACK) Option. Finden Sie in der Dokumentation auf diese Option, Weitere Informationen zu den *reservieren* und `commit` Argumente.

Diese Option wirkt sich nicht für DLLs aus.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)