---
title: Compilerfehler C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: e8f82ed4ce8ad77a22961a42c8e9a256e6f647db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535134"
---
# <a name="compiler-error-c2461"></a>Compilerfehler C2461

> "*Klasse*": Formale Parameterliste für Konstruktor fehlt

Der Konstruktor für die Klasse gibt keine formalen Parameter. Die Deklaration eines Konstruktors muss es sich um eine Liste formaler Parameter angeben. Die Liste kann leer sein.

Um dieses Problem zu beheben, fügen Sie ein Klammernpaar nach der Deklaration von *Klasse*:: **Klasse*.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie C2461 generiert Fehler beheben:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```