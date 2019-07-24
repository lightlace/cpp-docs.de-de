---
title: Compilerfehler C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 7fcf333f62253eb676c0f0ada1c927ab962ae1ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338921"
---
# <a name="compiler-error-c2441"></a>Compilerfehler C2441

> "*Variable*": ein mit __declspec(process) deklariertes Symbol muss const im/CLR: pure-Modus

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Variablen werden standardmäßig pro Anwendungsdomäne unter **/CLR: pure**. Markiert eine Variable `__declspec(process)` unter **/CLR: pure** fehleranfällig, wenn in einer Anwendungsdomäne geändert und in einer anderen gelesen wird.

Aus diesem Grund der Compiler erzwingt prozessspezifische Variablen `const` unter **/CLR: pure**, machen diese lesen in allen Anwendungsdomänen.

Weitere Informationen finden Sie unter [Prozess](../../cpp/process.md) und [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2441 generiert.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```