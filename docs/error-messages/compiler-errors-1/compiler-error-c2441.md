---
title: Compilerfehler C2441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4224d9090f3ace43f61a10c599fafa78d21600
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705279"
---
# <a name="compiler-error-c2441"></a>Compilerfehler C2441

> "*Variable*": ein Symbol mit __declspec(process) deklariertes muss const in/CLR: pure-Modus

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Standardmäßig sind Variablen pro Anwendungsdomäne unter **/CLR: pure**. Markiert eine Variable `__declspec(process)` unter **/CLR: pure** fehleranfällig, wenn in einer Anwendungsdomäne geändert und in einer anderen gelesen wird.

Aus diesem Grund erzwingt der Compiler prozessspezifische Variablen `const` unter **/CLR: pure**, machen sie lesen nur in allen Anwendungsdomänen.

Weitere Informationen finden Sie unter [Prozess](../../cpp/process.md) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2441 generiert.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```