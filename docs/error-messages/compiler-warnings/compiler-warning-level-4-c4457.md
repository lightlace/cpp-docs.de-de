---
title: Compilerwarnung (Stufe 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 11307ddc3b13a9cd9b36f1ee927082104792b07f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648356"
---
# <a name="compiler-warning-level-4-c4457"></a>Compilerwarnung (Stufe 4) C4457

> Deklaration von "*Bezeichner*" Blendet Funktionsparameter aus

Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet die Deklaration des Parameters der Funktion mit identischem Namen. Diese Warnung teilt Ihnen mitteilen, dass Verweise auf *Bezeichner* im lokalen Gültigkeitsbereich auf die lokal deklarierten Version nicht den Parameter, der nicht unbedingt Ihre Absicht zu beheben. Um dieses Problem zu beheben, empfehlen wir, dass Sie die lokalen Variablennamen, die nicht in Konflikt stehen mit Namen geben.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4457 generiert, da der Parameter `x` und die lokale Variable `x` in `member_fn` haben die gleichen Namen. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die Parameter und lokalen Variablen.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
