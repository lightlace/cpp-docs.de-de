---
title: Compilerfehler C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 656fcd8a1a0429546189de8c3f01ab928c6333ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587784"
---
# <a name="compiler-error-c2787"></a>Compilerfehler C2787

'Bezeichner': keine GUID dieses Objekt zugeordnet wurde

Die [__uuidof](../../cpp/uuidof-operator.md) -Operator akzeptiert einen benutzerdefinierten Typ mit einer GUID verbundenen oder ein Objekt eines solchen benutzerdefinierten Typs. Dieser Fehler tritt auf, wenn das Argument mit einem benutzerdefinierten Typ mit keine GUID ist.

Im folgende Beispiel wird die C2787 generiert:

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```