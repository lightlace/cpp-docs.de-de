---
title: Compilerfehler C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 0816fcb4d9e2a3e6588dfcf937383fed7ab11395
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737126"
---
# <a name="compiler-error-c2530"></a>Compilerfehler C2530

"Bezeichner": Verweise müssen initialisiert werden.

Sie müssen einen Verweis initialisieren, wenn er deklariert wurde, es sei denn, er ist bereits deklariert:

- Mit dem Schlüsselwort [extern](../../cpp/using-extern-to-specify-linkage.md).

- Als Member einer Klasse, Struktur oder Union (und im Konstruktor initialisiert).

- Als Parameter in einer Funktionsdeklaration oder-Definition.

- Als Rückgabetyp einer Funktion.

Im folgenden Beispiel wird C2530 generiert:

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
