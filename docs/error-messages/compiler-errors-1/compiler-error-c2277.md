---
title: Compilerfehler C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: d1c39203d8733b3992ed73172bb58fd7431e110a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759190"
---
# <a name="compiler-error-c2277"></a>Compilerfehler C2277

"Bezeichner": die Adresse dieser Member-Funktion kann nicht übernommen werden.

Sie können die Adresse einer Member-Funktion nicht übernehmen.

Im folgenden Beispiel wird C2277 generiert:

```cpp
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```
