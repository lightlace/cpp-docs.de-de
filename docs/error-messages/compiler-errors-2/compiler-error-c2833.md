---
title: Compilerfehler C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: c1467a3c67cccf28cc6b9bd0f987fe77b8da8988
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757877"
---
# <a name="compiler-error-c2833"></a>Compilerfehler C2833

"Operator Operator" ist kein bekannter Operator oder Typ.

Auf das Wort `operator` muss ein Operator folgen, den Sie überschreiben möchten, oder ein Typ, den Sie konvertieren möchten.

Eine Liste der Operatoren, die Sie in einem verwalteten Typ definieren können, finden Sie unter [benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).

Im folgenden Beispiel wird C2833 generiert:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
