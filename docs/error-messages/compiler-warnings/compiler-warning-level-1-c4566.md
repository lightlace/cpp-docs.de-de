---
title: Compilerwarnung (Stufe 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c864feb2478e9f99ad6e4c0087dcef72b55de601
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397262"
---
# <a name="compiler-warning-level-1-c4566"></a>Compilerwarnung (Stufe 1) C4566

Universelle Zeichennamen 'Char' dargestellte Zeichen kann nicht in der aktuellen Codepage (Seite) dargestellt werden

Nicht alle Unicode-Zeichen kann in der aktuellen ANSI-Codepage dargestellt werden.

Schmale Zeichenfolgen (1-Byte-Zeichen) werden in Multibyte-Zeichen konvertiert, während der Breite Zeichenfolgen (2-Byte-Zeichen) nicht sind.

Im folgende Beispiel wird die C4566 generiert:

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```