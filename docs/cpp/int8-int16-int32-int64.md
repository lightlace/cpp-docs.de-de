---
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 4e793f23581f7dc62a39fcd8c5c504fb5a2ccbc9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301469"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Microsoft-spezifisch**

Microsoft C/C++ bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Sie können 8-, 16-, 32-oder 64-Bit-ganzzahlige Variablen deklarieren, indem Sie den **__int**<em>n</em> -Typspezifizierer verwenden, wobei *n* 8, 16, 32 oder 64 ist.

Im folgenden Beispiel wird eine Variable für jeden dieser Typen von ganzen Zahlen mit angegebener Größe deklariert:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Die Typen **__int8**, **__int16**und **__int32** sind Synonyme für die ANSI-Typen, die die gleiche Größe aufweisen, und sind für das Schreiben von portablen Code nützlich, der sich auf mehreren Plattformen identisch verhält. Der **__int8** -Datentyp ist mit dem Typ " **char**" Synonym, **__int16** ist mit dem Typ " **Short**" Synonym und **__int32** ist mit dem Typ " **int**" Synonym. Der **__int64** Typ ist ein Synonym für den Typ " **Long Long**".

Aus Kompatibilitätsgründen mit früheren Versionen sind **_int8**, **_int16**, **_int32**und **_int64** Synonyme für **__int8**, **__int16**, **__int32**und **__int64** , es sei denn, die Compileroption [/Za \(Deaktivieren von Spracherweiterungen)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, dass ein __int*xx* -Parameter zu **int**herauf gestuft wird:

```cpp
// sized_int_types.cpp

#include <stdio.h>

void func(int i) {
    printf_s("%s\n", __FUNCTION__);
}

int main()
{
    __int8 i8 = 100;
    func(i8);   // no void func(__int8 i8) function
                // __int8 will be promoted to int
}
```

```Output
func
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Stichwörter](../cpp/keywords-cpp.md)<br/>
[Integrierte Typen](../cpp/fundamental-types-cpp.md)<br/>
[Datentypbereiche](../cpp/data-type-ranges.md)<br/>
