---
title: Compilerfehler C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 78b3d1a57d358eb11ba2f01ec184c5487a578228
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648317"
---
# <a name="compiler-error-c3734"></a>Compilerfehler C3734

„Klasse“: Eine verwaltete oder WinRT-Klasse kann kein „Co-Klasse“-Attribut sein.

Die [Co-Klasse](../../windows/coclass.md) Attribut kann nicht verwendet werden, mit verwalteten oder WinRT-Klassen.

Im folgenden Beispiel wird C3734 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
