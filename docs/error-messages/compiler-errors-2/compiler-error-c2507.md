---
title: Compilerfehler C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 23433dccd7fc4f86c2e848359ac50c796fcccab0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746798"
---
# <a name="compiler-error-c2507"></a>Compilerfehler C2507

' Identifier ': zu viele virtuelle Modifizierer für die Basisklasse.

Eine Klasse oder Struktur wird als `virtual` mehrmals deklariert. Nur ein `virtual` Modifizierer kann für jede Klasse in einer Liste von Basisklassen angezeigt werden.

Im folgenden Beispiel wird C2507 generiert:

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
