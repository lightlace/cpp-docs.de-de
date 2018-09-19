---
title: Compilerfehler C3857 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3857
dev_langs:
- C++
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 279ed343b57380df9db9180aa475e4d77ddf5ae5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097600"
---
# <a name="compiler-error-c3857"></a>Compilerfehler C3857

'Typ': mehrere Typparameterlisten sind nicht zulässig.

Mehr als eine Vorlage oder generisch wurde angegeben, für den gleichen Typ, was nicht zulässig ist.

Im folgende Beispiel wird die C3857 generiert:

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Mögliche Lösung:

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 kann auch auftreten, wenn Generika verwendet werden:

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Mögliche Lösung:

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```