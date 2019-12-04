---
title: Compilerfehler C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 1d3078614ff6818dd4185b3bd5ed2f49413db16f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755953"
---
# <a name="compiler-error-c3609"></a>Compilerfehler C3609

„Member“: Eine versiegelte oder endgültige Funktion muss virtuell sein.

Die Schlüsselwörter [versiegelt](../../extensions/sealed-cpp-component-extensions.md) und [endgültig](../../cpp/final-specifier.md) sind nur in einer Klasse, Struktur oder Element Funktion zulässig, die als `virtual`gekennzeichnet ist.

Im folgenden Beispiel wird C3609 generiert:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
