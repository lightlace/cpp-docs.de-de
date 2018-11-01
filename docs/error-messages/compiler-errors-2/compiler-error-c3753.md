---
title: Compilerfehler C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: b6b1e8c3241a778b29045e734fffebb663554e62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498370"
---
# <a name="compiler-error-c3753"></a>Compilerfehler C3753

eine generische Eigenschaft ist nicht zulässig.

Generische Parameterlisten können nur für verwaltete Klassen, Strukturen oder Funktionen angezeigt werden.

Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) und [Eigenschaft](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3753 generiert.

```
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```