---
title: Compilerfehler C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 00f2097dc556055f0becf1d81d784c9126c66f63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739596"
---
# <a name="compiler-error-c2787"></a>Compilerfehler C2787

"Bezeichner": diesem Objekt ist keine GUID zugeordnet.

Der [__uuidof](../../cpp/uuidof-operator.md) -Operator nimmt einen benutzerdefinierten Typ mit einer angefügten GUID oder einem Objekt eines solchen benutzerdefinierten Typs an. Dieser Fehler tritt auf, wenn es sich bei dem Argument um einen benutzerdefinierten Typ ohne GUID handelt.

Im folgenden Beispiel wird C2787 generiert:

```cpp
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```
