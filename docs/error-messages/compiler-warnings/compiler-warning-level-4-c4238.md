---
title: Compilerwarnung (Stufe 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: cc913a4f92963437347fbc708eca03c25ab9d403
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991465"
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
