---
title: Compilerwarnung (Stufe 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 5931516e3f4eba91c3b7a3ab4d0ca4979ce1ed84
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965923"
---
# <a name="compiler-warning-level-1-c4581"></a>Compilerwarnung (Stufe 1) C4581

veraltes Verhalten: "" Zeichenfolge1 "" wurde durch "Zeichenfolge2" zur Verarbeitung des Attributs ersetzt.

Dieser Fehler kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 durchgeführt wurde: C++ Parameter Überprüfung für visuelle Attribute.

In früheren Versionen wurden Attributwerte akzeptiert, unabhängig davon, ob Sie in Anführungszeichen eingeschlossen wurden. Wenn der Wert eine Enumeration ist, darf er nicht in Anführungszeichen eingeschlossen werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4581 generiert.

```cpp
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```