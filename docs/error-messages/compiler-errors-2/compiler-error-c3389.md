---
title: Compilerfehler C3389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b540f87458c75ddf7d57626b6251248652b96213
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704304"
---
# <a name="compiler-error-c3389"></a>Compilerfehler C3389

> __declspec (*Schlüsselwort*) kann nicht verwendet werden, mit/clr: pure oder/clr: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Ein [__declspec](../../cpp/declspec.md) Modifizierer impliziert einen prozessspezifischen Zustand.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) impliziert einen pro [Appdomain](../../cpp/appdomain.md) Zustand.  Daher Deklarieren einer Variablen mit der `keyword` **__declspec** Modifizierer und die Kompilierung mit **/CLR: pure** ist nicht zulässig.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3389 generiert:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```