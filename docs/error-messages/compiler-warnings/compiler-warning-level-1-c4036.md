---
title: Compilerwarnung (Stufe 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 632e88bb64568c97e937e83e177598054a954f22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609572"
---
# <a name="compiler-warning-level-1-c4036"></a>Compilerwarnung (Stufe 1) C4036

Unbenannter Typ 'Typ' als übergebener Parameter

Für eine Struktur, Union, Enumeration oder Klasse, die als übergebener Parameter verwendet wurde, ist kein Typname angegeben. Wenn Sie [/Zg](../../build/reference/zg-generate-function-prototypes.md) zum Generieren von Funktionsprototypen verwenden, gibt der Compiler diese Warnung aus und kommentiert den formalen Parameter im generierten Prototyp aus.

Geben Sie einen Typnamen an, um diese Warnung zu vermeiden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4036 generiert:

```
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```