---
title: Compilerfehler C2182
ms.date: 11/04/2016
f1_keywords:
- C2182
helpviewer_keywords:
- C2182
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
ms.openlocfilehash: da702087ad4d445d7fd4abe1956040a45b4414b6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737139"
---
# <a name="compiler-error-c2182"></a>Compilerfehler C2182

'bezeichner': Unzulässige Verwendung des Typs 'void'

Eine Variable ist als Typ `void`deklariert.

Im folgenden Beispiel wird C2182 generiert:

```cpp
// C2182.cpp
// compile with: /c
int main() {
   int i = 10;
   void &ir = i;   // C2182 cannot have a reference to type void
   int &ir = i;   // OK
}
```
