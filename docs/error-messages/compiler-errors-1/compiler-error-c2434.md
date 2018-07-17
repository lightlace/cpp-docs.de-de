---
title: Compilerfehler C2434 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45f9ccdef84713883c53dab0e7caf3b1519628de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704226"
---
# <a name="compiler-error-c2434"></a>Compilerfehler C2434

> "*Symbol*": ein Symbol mit __declspec(process) deklariertes kann nicht initialisiert werden, dynamisch in/CLR: pure-Modus

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Es ist nicht möglich, eine Variable pro-Prozess unter dynamisch zu initialisieren **/CLR: pure**. Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [Prozess](../../cpp/process.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2434 generiert. Um dieses Problem zu beheben, verwenden Sie Konstanten initialisieren `process` Variablen.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```