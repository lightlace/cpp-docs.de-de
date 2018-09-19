---
title: Compilerfehler C3519 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac9c1bfe01cee659ae8b637df23a86315b5310f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072783"
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