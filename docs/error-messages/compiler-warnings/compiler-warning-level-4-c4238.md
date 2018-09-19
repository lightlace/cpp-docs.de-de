---
title: Compilerwarnung (Stufe 4) C4238 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4d5f358d08f81e6b8097140ad47d54f4b3b3fed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057027"
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