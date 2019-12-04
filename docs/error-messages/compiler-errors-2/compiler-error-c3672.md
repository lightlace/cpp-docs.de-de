---
title: Compilerfehler C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: 3288f7ea0b95d141dd6b4281d7080de1409da606
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758098"
---
# <a name="compiler-error-c3672"></a>Compilerfehler C3672

der Pseudo destruktorausdruck kann nur als Teil eines Funktions Aufrufes verwendet werden.

Ein Dekonstruktor wurde falsch aufgerufen.  Weitere Informationen finden Sie unter [debugtoren](../../cpp/destructors-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3672 generiert.

```cpp
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```
