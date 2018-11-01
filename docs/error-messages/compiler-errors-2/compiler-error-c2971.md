---
title: Compilerfehler C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 09f3578bff5806fc32a3b5599dcfa8caa3696974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437296"
---
# <a name="compiler-error-c2971"></a>Compilerfehler C2971

'Klasse': Vorlagenparameter 'Param': 'Arg': eine lokale Variable kann nicht als Nichttyp Argument verwendet werden

Sie können nicht den Namen oder die Adresse einer lokalen Variablen als Vorlagenargument verwenden.

Im folgende Beispiel wird die C2971 generiert:

```
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```