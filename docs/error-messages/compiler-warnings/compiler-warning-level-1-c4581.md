---
title: Compilerwarnung (Stufe 1) C4581 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4581
dev_langs:
- C++
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 586283e41fb38baae828bf5a4380ec2afe323ecb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116047"
---
# <a name="compiler-warning-level-1-c4581"></a>Compilerwarnung (Stufe 1) C4581

Veraltetes Verhalten: "string1" ersetzt durch "Zeichenfolge2" zur Verarbeitung des Attributs

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual C++ 2005 durchgeführt wurde generiert werden: Überprüfen der Parameter für Visual C++-Attribute.

In früheren Versionen wurden Werte des Attributs akzeptiert, und zwar unabhängig davon, ob sie in Anführungszeichen eingeschlossen wäre. Wenn der Wert einer Enumeration ist, muss er nicht in Anführungszeichen eingeschlossen werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4581 generiert.

```
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