---
title: Compilerfehler C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: a5753fc99efcdb1064a21981c62faaba84d44189
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165585"
---
# <a name="compiler-error-c2500"></a>Compilerfehler C2500

'Bezeichner1': 'Bezeichner2' ist bereits eine direkte Basisklasse

Eine Klasse oder Struktur wird mehr als einmal in einer Liste der Basisklassen.

Eine direkte Basisklasse ist in der Basisliste aufgeführt sind. Eine indirekte Basisklasse ist eine Basisklasse von einer der Klassen in der Basisliste.

Eine Klasse kann nicht mehr als einmal als eine direkte Basisklasse angegeben werden. Eine Klasse kann mehrmals als indirekte Basisklasse verwendet werden.

Im folgende Beispiel wird die C2500 generiert:

```
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```