---
title: Compilerfehler C3862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b21e457feb6d090e4abaf531293987eb3504457
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704970"
---
# <a name="compiler-error-c3862"></a>Compilerfehler C3862

> "*Funktion*": kann nicht kompiliert werden eine nicht verwaltete Funktion mit/clr: pure oder/clr: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Eine Kompilierung mit **/CLR: pure** oder **/CLR: safe** erzeugt eine einzige MSIL-Images, die ein Bild ohne systemeigenen (nicht verwalteten) Code.  Aus diesem Grund können keine der `unmanaged` Pragma in einer **/CLR: pure** oder **/CLR: safe** Kompilierung.

Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3862 generiert:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```