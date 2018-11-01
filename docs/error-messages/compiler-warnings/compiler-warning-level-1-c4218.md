---
title: Compilerwarnung (Stufe 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 36d5de3b1270b41edfc391df960a556aca207709
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555297"
---
# <a name="compiler-warning-level-1-c4218"></a>Compilerwarnung (Stufe 1) C4218

nicht dem Standard entsprechende Erweiterung: müssen mindestens eine Speicherklasse oder einen Typ angeben

Mit den Standard-Microsoft-Erweiterungen (/ Ze) können Sie eine Variable deklarieren, ohne dass eine Klasse vom Typ oder Speicher. Der Standardtyp ist `int`.

## <a name="example"></a>Beispiel

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Derartige Deklarationen sind ungültige ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).