---
title: Compilerfehler C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: ceae17689cbcb9585fb3722580042187ff64a6ee
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755628"
---
# <a name="compiler-error-c3383"></a>Compilerfehler C3383

"operator new" wird mit /clr:safe nicht unterstützt.

Die Ausgabedatei einer **/clr:safe** -Kompilierung ist Datei, die überprüfbar typsicher ist; Zeiger werden nicht unterstützt.

Weitere Informationen finden Sie unter

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3383 generiert:

```cpp
// C3383.cpp
// compile with: /clr:safe
int main() {
   char* pCharArray = new char[256];  // C3383
}
```
