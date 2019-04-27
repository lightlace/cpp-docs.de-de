---
title: Compilerfehler C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 56c316ac971d0bdd1a0ca27ef8d4282acbe24779
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227675"
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