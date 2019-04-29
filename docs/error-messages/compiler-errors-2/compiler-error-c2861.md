---
title: Compilerfehler C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: bb61272b5a8d94a26096bd05260de331e853bf0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329074"
---
# <a name="compiler-error-c2861"></a>Compilerfehler C2861

"Funktionsname": eine Schnittstellenmemberfunktion kann nicht definiert werden

Der Compiler hat das Interface-Schlüsselwort oder eine Struktur als eine Schnittstelle abgeleitet gefunden dann jedoch eine Funktion der Definition.  Eine Schnittstelle kann nicht über eine Definition für eine Memberfunktion enthalten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2861 generiert:

```
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```