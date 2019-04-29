---
title: Compilerfehler C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: bb7d709f757b6da10c8b17d5b30e2c2b86edd85e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366094"
---
# <a name="compiler-error-c2991"></a>Compilerfehler C2991

Neudefinition des Typparameters „parameter“

Es ist ein Typenkonflikt zwischen zwei generischen oder Vorlagendefinitionen von `parameter`aufgetreten. Wenn Sie mehrere generische oder Vorlagenparameter definieren, müssen Sie äquivalente Typen verwenden.

Im folgenden Beispiel wird C2991 generiert:

```
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

C2991 kann auch auftreten, wenn Generics verwendet werden:

```
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```