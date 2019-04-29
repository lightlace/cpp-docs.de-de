---
title: Compilerwarnung (Stufe 4) C4458
ms.date: 11/04/2016
f1_keywords:
- C4458
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
ms.openlocfilehash: 9e5eb8dc44968332abc097bfbd16b48e3240695c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391451"
---
# <a name="compiler-warning-level-4-c4458"></a>Compilerwarnung (Stufe 4) C4458

> Deklaration von "*Bezeichner*" Blendet Klassenmember

Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet die Deklaration der identischen *Bezeichner* im Gültigkeitsbereich der Klasse. Diese Warnung teilt Ihnen mitteilen, dass Verweise auf *Bezeichner* in diesem Bereich zu beheben, auf die lokal deklarierten Version, die nicht Mitglied die Version der Klasse, die möglicherweise nicht Ihrer Absicht. Um dieses Problem zu beheben, empfehlen wir, dass Sie lokale Variablennamen, die keinen Konflikt mit Elementnamen Klasse geben.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4458 generiert, da der Parameter `x` und die lokale Variable `y` in `member_fn` haben die gleichen Namen wie die Datenmember in der Klasse. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die Parameter und lokalen Variablen.

```cpp
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;
        // To fix this issue, change the parameter name x
        // and local name y to something that does not
        // conflict with the data member names.
    }
} s;
```
