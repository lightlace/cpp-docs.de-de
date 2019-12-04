---
title: Compilerfehler C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 381bb59dae523c05cdc67e33ba9d326e247abc7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752859"
---
# <a name="compiler-error-c3734"></a>Compilerfehler C3734

'class': Eine verwaltete oder WinRT-Klasse kann kein „coclass“-Attribut sein.

Das [Co-Klasse](../../windows/coclass.md) -Attribut kann nicht für verwaltete oder WinRT-Klassen verwendet werden.

Im folgenden Beispiel wird C3734 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
