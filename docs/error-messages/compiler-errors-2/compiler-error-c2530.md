---
title: Compilerfehler C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474788"
---
# <a name="compiler-error-c2530"></a>Compilerfehler C2530

'Bezeichner': Verweise müssen initialisiert werden

Sie müssen einen Verweis initialisieren, bei der es deklariert wurde, es sei denn, die sie bereits deklariert ist:

- Mit dem Schlüsselwort ["extern"](../../cpp/using-extern-to-specify-linkage.md).

- Als Member einer Klasse, Struktur oder Union (und es wird im Konstruktor initialisiert).

- Als Parameter in einer Funktionsdeklaration oder-Definition.

- Als Rückgabetyp einer Funktion.

Im folgende Beispiel wird die C2530 generiert:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```