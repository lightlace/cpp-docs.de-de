---
title: Compilerfehler C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 56c316ac971d0bdd1a0ca27ef8d4282acbe24779
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490507"
---
# <a name="compiler-error-c2778"></a>Compilerfehler C2778

nicht ordnungsgemäß formatierte GUID in __declspec(UUID()) falsch formatiert

Eine falsche GUID angegeben wird, um die [Uuid](../../cpp/uuid-cpp.md) erweitertes Attribut.

Die GUID muss es sich um eine Zeichenfolge aus hexadezimalen Zahlen mit dem folgenden Format sein:

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

Die `uuid` erweitertes Attribut akzeptiert von [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring)mit oder ohne Klammern eingeschlossen.

Im folgende Beispiel wird die C2778 generiert:

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```