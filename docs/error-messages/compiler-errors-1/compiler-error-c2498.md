---
title: Compilerfehler C2498
ms.date: 11/04/2016
f1_keywords:
- C2498
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
ms.openlocfilehash: 2b6f6469a221c914e0eef9e190c79a2b2706e651
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756993"
---
# <a name="compiler-error-c2498"></a>Compilerfehler C2498

"Function": "novtable" kann nur auf Klassen Deklarationen oder Definitionen angewendet werden.

Dieser Fehler kann durch die Verwendung von `__declspec(novtable)` mit einer Funktion verursacht werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2498 generiert:

```cpp
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```
