---
title: __alignof-Operator
ms.date: 12/17/2018
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 96c85db83c133af6f1712baa8597ed3360277854
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627415"
---
# <a name="alignof-operator"></a>__alignof-Operator

C ++ 11 stellt die **"alignof"** Operator, der die Ausrichtung des angegebenen Typs in Bytes zurückgibt. Zur maximalen Portabilität sollten Sie den „alignof“ des Operators statt des Microsoft-spezifischen „__alignof“-Operators verwenden.

**Microsoft-spezifisch**

Gibt einen Wert vom Typ `size_t` , der der ausrichtungsanforderung des Typs.

## <a name="syntax"></a>Syntax

```cpp
  __alignof( type )
```

## <a name="remarks"></a>Hinweise

Zum Beispiel:

|Ausdruck|Wert|
|----------------|-----------|
|**__alignof (Char)**|1|
|**__alignof (kurz)**|2|
|**__alignof (Int)**|4|
|**__alignof ( \___int64)**|8|
|**__alignof( float )**|4|
|**__alignof (Double)**|8|
|**__alignof( char\* )**|4|

Die **__alignof** Wert entspricht der Wert für `sizeof` für grundlegende Typen. Betrachten Sie jedoch das Beispiel:

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

In diesem Fall die **__alignof** Wert ist die ausrichtungsanforderung des größten Elements in der Struktur.

Entsprechend gilt:

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` ist gleich `32`.

Eine Verwendungsmöglichkeit für **__alignof** wäre als Parameter an eine der eigene speicherbelegungsroutinen. Beispielsweise könnten Sie angesichts der folgenden definierten Struktur `S` eine Speicherbelegungsroutine mit dem Namen `aligned_malloc` aufrufen, um einen bestimmten Grenzwert mit Speicher zu belegen.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

Für die Kompatibilität mit früheren Versionen **_alignof** ist ein Synonym für **__alignof** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

Weitere Informationen über das Ändern der Ausrichtung finden Sie unter:

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md)

- [Beispiele für die Strukturausrichtung](../build/x64-software-conventions.md#examples-of-structure-alignment) (X64 bestimmte)

Weitere Informationen zu den Unterschieden bei der Ausrichtung im Code für x86 und x64 finden Sie unter:

- [Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)