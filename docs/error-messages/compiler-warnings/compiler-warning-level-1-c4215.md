---
title: Compilerwarnung (Stufe 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: 91be04f927c63ccbb0668bbe70cbd7c5813f8dfc
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627351"
---
# <a name="compiler-warning-level-1-c4215"></a>Compilerwarnung (Stufe 1) C4215

nicht dem Standard entsprechende Erweiterung: Long float

Die standardmäßigen Microsoft-Erweiterungen (/Ze) behandeln **Long float** als **Double**. Die ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ist nicht. Verwenden Sie **Double** , um die Kompatibilität aufrechtzuerhalten.

Im folgenden Beispiel wird C4215 generiert:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```