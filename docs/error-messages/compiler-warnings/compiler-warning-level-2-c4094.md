---
title: Compilerwarnung (Stufe 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c293522e5d60d0edb4cc2da289e0ece71f89329f
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052199"
---
# <a name="compiler-warning-level-2-c4094"></a>Compilerwarnung (Stufe 2) C4094

nicht markierte ' Token ' deklariert keine Symbole

Der Compiler hat eine leere Deklaration mit einer nicht markierten Struktur, Union oder Klasse erkannt. Die Deklaration wird ignoriert.

## <a name="example"></a>Beispiel

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Diese Bedingung generiert einen Fehler unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).