---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: 5f0c23ad8b8d81f888616042ee5d6ba5bc63bd44
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412873"
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
