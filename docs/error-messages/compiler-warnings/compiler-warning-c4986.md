---
title: Compilerwarnung C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: fb52e33ceeadda03105e391d8e0b5b3f6234d6b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280593"
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