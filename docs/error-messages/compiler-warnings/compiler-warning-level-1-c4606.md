---
title: Compilerwarnung (Stufe 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: e471ca3e478d1166b150e49bf25efa4b9d5803cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569272"
---
# <a name="compiler-warning-level-1-c4606"></a>Compilerwarnung (Stufe 1) C4606

\#Pragma-Warnung: "warning_number ' wurde ignoriert. Codeanalysewarnungen sind keinen Warnstufen zugeordnet

Für die Codeanalyse, nur Warnungen `error`, `once`, und `default` werden unterstützt, mit der [Warnung](../../preprocessor/warning.md) Pragma.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4606 generiert.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```