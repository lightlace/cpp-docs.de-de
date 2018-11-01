---
title: Compilerfehler C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 9c9772052b690ad87de1d408c06478d82d48e724
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464804"
---
# <a name="compiler-error-c2652"></a>Compilerfehler C2652

'Bezeichner': Unzulässiger Kopierkonstruktor: erster Parameter darf nicht 'Bezeichner' sein

Der erste Parameter in der Kopierkonstruktor hat denselben Typ wie die Klasse, Struktur oder Union, die für die sie definiert ist. Der erste Parameter kann einen Verweis auf den Typ, aber nicht den Typ selbst sein.

Im folgende Beispiel wird die C2651 generiert:

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```