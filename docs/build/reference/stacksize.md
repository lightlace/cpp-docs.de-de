---
title: STACKSIZE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9b61febedde1a2647df6312a8588b08c6bdad7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705561"
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