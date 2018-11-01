---
title: Compilerfehler C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 9e24fc28f84bfacb7478d700047c4eb1363247de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451271"
---
# <a name="compiler-error-c3246"></a>Compilerfehler C3246

'klasse': Von 'typ' kann nicht geerbt werden, da er als 'sealed' (versiegelt) deklariert wurde

Eine Klasse, die als [versiegelt](../../windows/sealed-cpp-component-extensions.md) gekennzeichnet ist, kann nicht die Basisklasse für andere Klassen bilden.

Im folgenden Beispiel wird C3246 generiert:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
