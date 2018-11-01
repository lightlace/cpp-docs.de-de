---
title: Compilerwarnung (Stufe 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471902"
---
# <a name="compiler-warning-level-4-c4238"></a>Compilerwarnung (Stufe 4) C4238

nicht dem Standard entsprechende Erweiterung: Klasse Rvalue verwendet als l-Wert

Für die Kompatibilität mit früheren Versionen von Visual C++, Microsoft-Erweiterungen (**/Ze**) ermöglichen es Ihnen, einen Klassentyp zu verwenden, wie ein Rvalue-Wert in einem Kontext, der implizit oder explizit auf die Adresse akzeptiert. In einigen Fällen, wie im folgenden Beispiel kann dies gefährlich sein.

## <a name="example"></a>Beispiel

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Diese Verwendung verursacht einen Fehler ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).