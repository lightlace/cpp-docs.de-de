---
title: Compilerwarnung (Stufe 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: 6387f58430098e49e7add25e8915bf6b181634e9
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541840"
---
# <a name="compiler-warning-level-4-c4211"></a>Compilerwarnung (Stufe 4) C4211

nicht dem Standard entsprechende Erweiterung: Neudefinition von extern in static

Mit den standardmäßigen Microsoft-Erweiterungen (/Ze) können Sie einen `extern` Bezeichner als **statisch**neu definieren.

## <a name="example"></a>Beispiel

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

Diese Neudefinitionen sind unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ungültig.
