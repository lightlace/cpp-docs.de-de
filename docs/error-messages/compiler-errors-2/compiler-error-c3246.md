---
title: Compilerfehler C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: eb5ba268508922daf00adb49cf611c038db76343
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173196"
---
# <a name="compiler-error-c3246"></a>Compilerfehler C3246

'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' (versiegelt) deklariert wurde

Eine Klasse, die als [versiegelt](../../extensions/sealed-cpp-component-extensions.md) gekennzeichnet ist, kann nicht die Basisklasse für andere Klassen bilden.

Im folgenden Beispiel wird C3246 generiert:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
