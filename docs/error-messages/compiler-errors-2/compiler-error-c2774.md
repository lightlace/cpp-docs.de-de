---
title: Compilerfehler C2774
ms.date: 11/04/2016
f1_keywords:
- C2774
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
ms.openlocfilehash: 2630dba6a74bf6b31a5df7af57e42fd7c8fd4e09
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740103"
---
# <a name="compiler-error-c2774"></a>Compilerfehler C2774

"Bezeichner": keine "Put"-Methode mit dieser Eigenschaft verknüpft

Ein Datenmember, der mit der- [Eigenschaft](../../cpp/property-cpp.md) deklariert wurde, hat keine `put`-Funktion, aber ein Ausdruck versucht, seinen Wert festzulegen.

Im folgenden Beispiel wird C2774 generiert:

```cpp
// C2774.cpp
struct A {
   __declspec(property(get=GetProp)) int prop;
   int GetProp(void);

   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;
   int GetProp2(void);
   void PutProp2(int);
};

int main() {
   A* pa = new A;
   int val = 0;
   pa->prop = val;   // C2774
   pa->prop++;   // C2774
}
```
