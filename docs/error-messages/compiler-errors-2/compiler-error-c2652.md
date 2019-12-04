---
title: Compilerfehler C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: cedee3f1e3289aaf0ea38d75b6c812b61f891435
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756122"
---
# <a name="compiler-error-c2652"></a>Compilerfehler C2652

"Bezeichner": Unzulässiger Kopierkonstruktor: der erste Parameter darf kein "Bezeichner" sein.

Der erste Parameter im Kopierkonstruktor hat denselben Typ wie die Klasse, Struktur oder Union, für die er definiert ist. Der erste Parameter kann ein Verweis auf den Typ sein, jedoch nicht auf den Typ selbst.

Im folgenden Beispiel wird C2651 generiert:

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```
