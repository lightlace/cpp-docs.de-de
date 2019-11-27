---
title: Compilerwarnung (Stufe 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 982457ded987f6aee4f2891bbb7d9103b830cc99
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541786"
---
# <a name="compiler-warning-level-4-c4238"></a>Compilerwarnung (Stufe 4) C4238

nicht dem Standard entsprechende Erweiterung: Klasse "Rvalue" wird als "lvalue" verwendet

Aus Kompatibilitätsgründen mit früheren Versionen C++von Visual können Sie mithilfe von Microsoft-Erweiterungen ( **/Ze**) einen Klassentyp als Rvalue in einem Kontext verwenden, der implizit oder explizit seine Adresse annimmt. In einigen Fällen, wie z. b. im folgenden Beispiel, kann dies gefährlich sein.

## <a name="example"></a>Beispiel

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Diese Verwendung verursacht einen Fehler unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).