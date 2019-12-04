---
title: Compilerfehler C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 152546fce8f3ee63f8b95595bff052f18cd4ebda
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746967"
---
# <a name="compiler-error-c2500"></a>Compilerfehler C2500

' Bezeichner1 ': ' Bezeichner2 ' ist bereits eine direkte Basisklasse

Eine Klasse oder Struktur wird in einer Liste von Basisklassen mehrmals angezeigt.

Eine direkte Basis ist eine, die in der Basisliste erwähnt wird. Eine indirekte Basis ist eine Basisklasse für eine der Klassen in der Basisliste.

Eine Klasse kann nicht mehr als einmal als direkte Basisklasse angegeben werden. Eine Klasse kann mehrmals als indirekte Basisklasse verwendet werden.

Im folgenden Beispiel wird C2500 generiert:

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
