---
title: Compilerwarnung (Stufe 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 858cf089d3f681438a221115c8758c38a5cf8d9a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626264"
---
# <a name="compiler-warning-level-1-c4036"></a>Compilerwarnung (Stufe 1) C4036

Unbenannter Typ 'Typ' als übergebener Parameter

Für eine Struktur, Union, Enumeration oder Klasse, die als übergebener Parameter verwendet wurde, ist kein Typname angegeben. Wenn Sie [/Zg](../../build/reference/zg-generate-function-prototypes.md) zum Generieren von Funktionsprototypen verwenden, gibt der Compiler diese Warnung aus und kommentiert den formalen Parameter im generierten Prototyp aus.

Geben Sie einen Typnamen an, um diese Warnung zu vermeiden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4036 generiert:

```c
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```