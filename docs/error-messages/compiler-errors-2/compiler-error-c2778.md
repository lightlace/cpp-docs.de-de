---
title: Compilerfehler C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 247aba1b4dfe6b6d6db1e2b8f46f2aa08abf1a79
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739986"
---
# <a name="compiler-error-c2778"></a>Compilerfehler C2778

falsch formatierte GUID in __declspec (UUID ())

Für das erweiterte [UUID](../../cpp/uuid-cpp.md) -Attribut wird eine falsche GUID angegeben.

Die GUID muss eine Zeichenfolge von hexadezimalen Zahlen im folgenden Format sein:

```cpp
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

Das erweiterte `uuid`-Attribut akzeptiert Zeichen folgen, die von [CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)erkannt werden, mit oder ohne geschweifter Klammer Trennzeichen.

Im folgenden Beispiel wird C2778 generiert:

```cpp
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```
