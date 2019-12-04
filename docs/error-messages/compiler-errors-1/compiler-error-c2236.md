---
title: Compilerfehler C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: f61c5cd6da036d54c6184871deb45fed0210c48a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759229"
---
# <a name="compiler-error-c2236"></a>Compilerfehler C2236

Unerwartetes Token 'Bezeichner'. Haben Sie ein ';' vergessen?

Der Bezeichner wurde bereits als Typ definiert und kann nicht durch einen benutzerdefinierten Typ überschrieben werden.

Das folgende Beispiel generiert C2236:

```cpp
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```
