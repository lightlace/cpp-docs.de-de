---
title: Compilerwarnung (Stufe 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: dd1db3cccf9f1b24f82ddddf10fcf35f39a9251a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988794"
---
# <a name="compiler-warning-level-4-c4932"></a>Compilerwarnung (Stufe 4) C4932

__identifier (Bezeichner) und \__identifier (Bezeichner) sind nicht unterscheidbar.

Der Compiler kann bei dem an **__identifier** übergebenen Parameter nicht zwischen `__finally` _finally `__try` und **oder** und [_try](../../extensions/identifier-cpp-cli.md)unterscheiden. Sie sollten nicht beide Bezeichner im selben Programm verwenden, weil dadurch der Fehler [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) verursacht wird.

Im folgenden Beispiel wird C4932 generiert:

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
