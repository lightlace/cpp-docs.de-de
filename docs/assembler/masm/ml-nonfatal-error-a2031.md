---
title: Schwerwiegender ML--Fehler A2031 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2031
dev_langs:
- C++
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf6744224847e114e76df6e7ad6470696d3e8387
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682657"
---
# <a name="ml-nonfatal-error-a2031"></a>Nicht schwerwiegender ML-Fehler A2031

**Index oder die Basis-Register müssen sein werden.**

Es wurde versucht, auf ein Register verwenden, die kein Basis- oder Indexregister in einem Speicher-Ausdruck.

Dieser Fehler wird beispielsweise die folgenden Ausdrücke verursacht:

```asm
[ax]
[bl]
```

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>