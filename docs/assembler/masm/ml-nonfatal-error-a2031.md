---
title: Nicht schwerwiegender ML-Fehler A2031
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: f964c67ba7bf399e9a3761e4e201662a6a712a1b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856700"
---
# <a name="ml-nonfatal-error-a2031"></a>Nicht schwerwiegender ML-Fehler A2031

**muss ein Index-oder Basisregister sein.**

Es wurde versucht, ein Register zu verwenden, das kein Basis-oder Indexregister in einem Speicher Ausdruck war.

Die folgenden Ausdrücke verursachen beispielsweise diesen Fehler:

```asm
[ax]
[bl]
```

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>