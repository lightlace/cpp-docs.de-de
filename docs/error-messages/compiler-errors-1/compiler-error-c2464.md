---
title: Compilerfehler C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: e4952f4702d871ecf1c818b1fc7394e54a1a295f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743886"
---
# <a name="compiler-error-c2464"></a>Compilerfehler C2464

"Bezeichner": "New" kann nicht zum Zuordnen eines Verweises verwendet werden.

Mit dem `new`-Operator wurde ein Verweis Bezeichner zugeordnet. Verweise sind keine Speicher Objekte, sodass `new` keinen Zeiger darauf zurückgeben kann. Verwenden Sie die standardmäßige Variablen Deklarations Syntax zum Deklarieren eines Verweises.

Im folgenden Beispiel wird C2464 generiert:

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
