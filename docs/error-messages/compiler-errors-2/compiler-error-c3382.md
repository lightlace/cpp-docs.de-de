---
title: Compilerfehler C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 419577ddd5b5d7d2d21a91f500070cb190c72117
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760464"
---
# <a name="compiler-error-c3382"></a>Compilerfehler C3382

"sizeof" wird von /clr:safe nicht unterstützt.

Die Ausgabedatei einer **/clr:safe** -Kompilierung ist eine überprüfbar typsichere Datei, und „sizeof“ wird nicht unterstützt, weil der Rückgabewert des sizeof-Operators „size_t“ lautet und seine Größe je nach Betriebssystem variiert.

Weitere Informationen finden Sie unter

- [sizeof-Operator](../../cpp/sizeof-operator.md)

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3382 generiert:

```cpp
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```
