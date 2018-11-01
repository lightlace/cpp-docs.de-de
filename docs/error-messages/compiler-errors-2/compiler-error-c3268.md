---
title: Compilerfehler C3268
ms.date: 11/04/2016
f1_keywords:
- C3268
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
ms.openlocfilehash: c766488b29273f321feffa8e38a97e54454db7b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480534"
---
# <a name="compiler-error-c3268"></a>Compilerfehler C3268

> "*Funktion*': eine generische Funktion oder eine Memberfunktion einer generischen Klasse kann keine Variablenparameterliste haben

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3268 generiert:

```cpp
// C3268.cpp
// compile with: /clr:pure /c
generic <class ItemType>
void Test(ItemType item, ...) {}   // C3268
// try the following line instead
// void Test(ItemType item) {}

generic <class ItemType2>
ref struct MyStruct { void Test(...){} };   // C3268
// try the following line instead
// ref struct MyStruct { void Test2(){} };   // OK
```