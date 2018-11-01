---
title: Compilerfehler C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: 296224532b19d9ff85c8644aa653b6d842205213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622819"
---
# <a name="compiler-error-c2892"></a>Compilerfehler C2892

lokale Klasse darf keine Membervorlagen haben.

Auf Vorlagen basierenden Member-Funktionen sind nicht gültig, in einer Klasse, die in einer Funktion definiert ist.

Im folgende Beispiel wird die C2892 generiert:

```
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```