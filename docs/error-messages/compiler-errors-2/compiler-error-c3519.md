---
title: Compilerfehler C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: e9a998e1c3a6c2fb770fb9d26d97b8a24e5554d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360033"
---
# <a name="compiler-error-c3519"></a>Compilerfehler C3519

'Invalid_param': Ungültiger Parameter für das Embedded_idl-Attribut

Ein Parameter übergebene der `embedded_idl` Attribut des [#import](../../preprocessor/hash-import-directive-cpp.md), aber der Compiler hat den Parameter nicht erkannt.

Die einzigen Parameter, die für dürfen `embedded_idl` sind `emitidl` und `no_emitidl`.

Im folgende Beispiel wird die C3519 generiert:

```
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```