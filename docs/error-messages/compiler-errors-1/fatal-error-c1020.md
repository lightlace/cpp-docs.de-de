---
title: Schwerwiegender Fehler C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 67cf5067c85d07215f6391d9e5d3d1bcb4978e42
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756902"
---
# <a name="fatal-error-c1020"></a>Schwerwiegender Fehler C1020

Unerwartetes #endif

Die `#endif` -Direktive hat keine entsprechende `#if`-, `#ifdef`- oder `#ifndef` -Direktive. Stellen Sie sicher, dass jede `#endif` -Direktive über eine entsprechende Direktive verfügt.

Im folgenden Beispiel wird C1020 generiert:

```cpp
// C1020.cpp
#endif     // C1020
```

Mögliche Lösung:

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
