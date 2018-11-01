---
title: Compilerfehler C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: c73a8d4fcde945ddf2495cc2d0d7dc47216f2db3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587589"
---
# <a name="compiler-error-c2434"></a>Compilerfehler C2434

> "*Symbol*": ein mit __declspec(process) deklariertes Symbol kann nicht dynamisch initialisiert werden, im/CLR: pure-Modus

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Es ist nicht möglich, eine Variable pro Prozess unter dynamisch initialisiert **/CLR: pure**. Weitere Informationen finden Sie unter [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [Prozess](../../cpp/process.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2434 generiert. Um dieses Problem zu beheben, verwenden Sie Konstanten zum Initialisieren `process` Variablen.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```