---
title: Compilerfehler C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408367"
---
# <a name="compiler-error-c2833"></a>Compilerfehler C2833

'Operator Operator' ist kein bekannter Operator oder Typ

Das Wort `operator` muss ein Operator, der Sie überschreiben möchten oder ein Typ, die Sie konvertieren möchten folgen.

Eine Liste der Operatoren, die Sie in einem verwalteten Typ definieren können, finden Sie unter [benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).

Im folgende Beispiel wird die C2833 generiert:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```