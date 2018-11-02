---
title: Compilerfehler C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531819"
---
# <a name="compiler-error-c2812"></a>Compilerfehler C2812

> \#Import wird nicht unterstützt, mit/clr: pure und/CLR: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

[#import-Anweisung](../../preprocessor/hash-import-directive-cpp.md) wird nicht unterstützt **/CLR: pure** und **/CLR: safe** da `#import` erfordert die Verwendung von native-Compiler-Unterstützungsbibliotheken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2812 generiert.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```