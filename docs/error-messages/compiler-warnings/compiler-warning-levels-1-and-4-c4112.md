---
title: Compilerwarnung (Stufen 1 und 4) C4112
ms.date: 11/04/2016
f1_keywords:
- C4112
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
ms.openlocfilehash: f614373e1b96de2c8167d7981c0a87a4e1c58435
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991230"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Compilerwarnung (Stufen 1 und 4) C4112

für \#Zeile ist eine Ganzzahl zwischen 1 und Zahl erforderlich.

Die [#line](../../preprocessor/hash-line-directive-c-cpp.md) -Direktive gibt einen ganzzahligen Parameter an, der außerhalb des zulässigen Bereichs liegt.

Wenn der angegebene Parameter kleiner als 1 ist, wird der Zeilenzähler auf 1 zurückgesetzt. Wenn der angegebene Parameter größer als *Anzahl*ist, der vom Compiler definierte Grenzwert, bleibt der Zeilenzähler unverändert. Dies ist eine Warnung der Stufe 1 unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung der Stufe 4 gemäß Microsoft-Extensions ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Im folgenden Beispiel wird C4112 generiert:

```cpp
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```
