---
title: Compilerfehler C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: f3868a44cf04d6c87092759ea473aa78aa0ad4c4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760888"
---
# <a name="compiler-error-c2892"></a>Compilerfehler C2892

lokale Klasse darf keine Element Vorlagen aufweisen

Auf Vorlagen basierende Member-Funktionen sind in einer Klasse, die in einer Funktion definiert ist, ungültig.

Im folgenden Beispiel wird C2892 generiert:

```cpp
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
