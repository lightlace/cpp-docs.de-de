---
title: Compilerfehler C2970
ms.date: 11/04/2016
f1_keywords:
- C2970
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
ms.openlocfilehash: af30ccc4a71c51d042d6f7807a648a1eef066a70
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742664"
---
# <a name="compiler-error-c2970"></a>Compilerfehler C2970

' class ': Vorlagen Parameter ' param ': ' arg ': ein Ausdruck, der Objekte mit interner Verknüpfung umfasst, kann nicht als Nichttyp-Argument verwendet werden.

Der Name oder die Adresse einer statischen Variablen kann nicht als Vorlagen Argument verwendet werden. Die Vorlagen Klasse erwartet einen konstanten Wert, der zur Kompilierzeit ausgewertet werden kann.

Im folgenden Beispiel wird C2970 generiert:

```cpp
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```
