---
title: Compilerfehler C2500 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b7e24ca520796b63171fe63c2bf841fe8776845
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026672"
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