---
title: Compilerwarnung (Stufe 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: 1f029d7717f99e55a977ad9cb80dacbfa1485086
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541212"
---
# <a name="compiler-warning-level-4-c4201"></a>Compilerwarnung (Stufe 4) C4201

nicht dem Standard entsprechende Erweiterung: namenlose Struktur/Union

Unter Microsoft Extensions (/Ze) können Sie eine Struktur ohne Deklarator als Member einer anderen Struktur oder Union angeben. Diese Strukturen generieren einen Fehler unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Beispiel

```cpp
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```