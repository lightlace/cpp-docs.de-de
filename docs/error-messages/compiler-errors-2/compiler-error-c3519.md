---
title: Compilerfehler C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: 7e56ff814b1a2dd6ec3cb41db2cbcc21d7dcf2d9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750168"
---
# <a name="compiler-error-c3519"></a>Compilerfehler C3519

' Invalid_param ': Ungültiger Parameter für embedded_idl Attribut.

Es wurde ein Parameter an das `embedded_idl`-Attribut [#Import](../../preprocessor/hash-import-directive-cpp.md)übergeben, aber der Compiler hat den Parameter nicht erkannt.

Die einzigen für `embedded_idl` zulässigen Parameter sind `emitidl` und `no_emitidl`.

Im folgenden Beispiel wird C3519 generiert:

```cpp
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```
