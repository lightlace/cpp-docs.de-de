---
title: Nicht schwerwiegender ML-Fehler A2031
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: 794fb31fbc22bdefddf9f19e6efcb3c34bbc1861
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177681"
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