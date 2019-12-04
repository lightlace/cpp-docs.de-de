---
title: Compilerfehler C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 3d6cab186d4acf229a32620f33c9c86e807459dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751988"
---
# <a name="compiler-error-c2861"></a>Compilerfehler C2861

"Funktionsname": eine Schnittstellenmember-Funktion kann nicht definiert werden.

Der Compiler hat das Schnittstellen Schlüsselwort gefunden oder eine Struktur als Schnittstelle abgeleitet, aber dann eine Element Funktionsdefinition gefunden.  Eine Schnittstelle kann keine Definition für eine Element Funktion enthalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2861 generiert:

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```
