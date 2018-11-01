---
title: Compilerfehler C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: ac45847c94e7d2dc731eba71b0a38105eb915e53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590410"
---
# <a name="compiler-error-c3062"></a>Compilerfehler C3062

"Enum": Enumerator ist ein Wert erforderlich, da der zugrunde liegenden Typ 'Typ'

Sie können einen zugrunde liegenden Typ für eine Enumeration angeben. Allerdings erfordern einige Typen Zuweisen von Werten für jeden Enumerator.

Weitere Informationen über Enumerationen finden Sie unter [Enumerationsklasse](../../windows/enum-class-cpp-component-extensions.md).

Im folgende Beispiel wird die C3062 generiert:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```