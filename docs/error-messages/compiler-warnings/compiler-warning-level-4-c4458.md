---
title: Compilerwarnung (Stufe 4) C4458 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 873aa94db899ae6620e2bbb1f24277c6e7c841c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094545"
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
