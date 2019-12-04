---
title: Compilerfehler C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: e9396b3bc5eea5d15366fc94ffa308d78754c31e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754393"
---
# <a name="compiler-error-c3246"></a>Compilerfehler C3246

'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' (versiegelt) deklariert wurde

Eine Klasse, die als [versiegelt](../../extensions/sealed-cpp-component-extensions.md) gekennzeichnet ist, kann nicht die Basisklasse für andere Klassen bilden.

Im folgenden Beispiel wird C3246 generiert:

```cpp
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
