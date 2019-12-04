---
title: Compilerfehler C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 3046d7009d2a54bab6d4d9acf0706335ae9d1974
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761005"
---
# <a name="compiler-error-c2923"></a>Compilerfehler C2923

"Typ": "Bezeichner" ist kein gültiges Vorlagentypargument für den "param"-Parameter

In der Argumentliste fehlt ein Typ, der zur Instanziierung der Vorlage oder des Generikums erforderlich ist. Überprüfen Sie die Vorlage oder die generische Deklaration.

Im folgenden Beispiel wird C2923 generiert:

```cpp
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

C2923 kann auch auftreten, wenn Generics verwendet werden:

```cpp
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```
