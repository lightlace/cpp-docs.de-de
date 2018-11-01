---
title: Compilerfehler C3455
ms.date: 11/04/2016
f1_keywords:
- C3455
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
ms.openlocfilehash: 4451ddbd8d5a7125112ef8e1c58e8843095bffd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614395"
---
# <a name="compiler-error-c3455"></a>Compilerfehler C3455

'attribut': Keiner der Attributkonstruktoren stimmte mit den Argumenten überein.

Ein ungültiger Wert wurde verwendet, um ein Attribut zu deklarieren.  Weitere Informationen finden Sie unter [attribute](../../windows/attributes/attribute.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3455 generiert:

```
// C3455.cpp
// compile with: /clr /c
using namespace System;

[attribute("MyAt")]   // C3455
// try the following line instead
// [attribute(All)]
ref struct MyAttr {
   MyAttr() {}
};
```