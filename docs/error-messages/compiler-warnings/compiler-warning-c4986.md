---
title: Compilerwarnung C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: fb52e33ceeadda03105e391d8e0b5b3f6234d6b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499124"
---
# <a name="compiler-warning-c4986"></a>Compilerwarnung C4986

'Funktion': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein

Diese Warnung kann generiert werden, wenn eine Ausnahmespezifikation, die in einer Deklaration und nicht in der anderen vorhanden ist.

Standardmäßig ist C4986 deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4986 generiert.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel beseitigt diese Warnung.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```