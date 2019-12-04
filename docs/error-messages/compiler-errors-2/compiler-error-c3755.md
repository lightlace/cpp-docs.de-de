---
title: Compilerfehler C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 0150693ae84b45dc62c11cfdc59369eb25a819cd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757279"
---
# <a name="compiler-error-c3755"></a>Compilerfehler C3755

"Delegat": ein Delegat kann nicht definiert werden.

Ein Delegat [(C++ Komponenten Erweiterungen)](../../extensions/delegate-cpp-component-extensions.md) kann deklariert, aber nicht definiert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3755 generiert.

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>Beispiel

C3755 kann auch auftreten, wenn Sie versuchen, eine Delegatvorlage zu erstellen. Im folgenden Beispiel wird C3755 generiert.

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
