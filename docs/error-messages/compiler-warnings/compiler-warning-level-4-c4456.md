---
title: Compilerwarnung (Stufe 4) C4456 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab6939fe37260b906a43c4e2ff6683733348952
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039893"
---
# <a name="compiler-warning-level-4-c4456"></a>Compilerwarnung (Stufe 4) C4456

> Deklaration von "*Bezeichner*" Blendet vorherige lokale Deklaration

Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet die Deklaration der frühere lokalen Deklaration mit demselben Namen. Diese Warnung teilt Ihnen mitteilen, dass Verweise auf *Bezeichner* im lokalen Gültigkeitsbereich aufgelöst, auf die lokal deklarierten Version, die nicht dem vorherigen lokalen, die möglicherweise nicht Ihrer Absicht. Um dieses Problem zu beheben, empfehlen wir, dass Sie die lokalen Variablennamen, die keinen Konflikt mit anderen lokalen Namen geben.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C4456, da die Steuerung von Schleifen Variable `int x` und die lokale Variable `double x` in `member_fn` haben die gleichen Namen. Um dieses Problem zu beheben, verwenden Sie unterschiedliche Namen für die lokalen Variablen.

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
