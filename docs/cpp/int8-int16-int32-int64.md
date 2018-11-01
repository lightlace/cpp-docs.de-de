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
ms.openlocfilehash: b765eabcac3f9643c0cae78fefb6ce8231669ffc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617307"
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64

**Microsoft-spezifisch**

Microsoft C/C++ bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. 8, 16-, 32- oder 64-Bit-Ganzzahl-Variablen deklarieren Sie mithilfe der **__int**<em>n</em> Typspezifizierer verwenden, wobei *n* ist 8, 16, 32 oder 64.

Im folgenden Beispiel wird eine Variable für jeden dieser Typen von ganzen Zahlen mit angegebener Größe deklariert:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Die Typen **__int8**, **__int16**, und **__int32** sind Synonyme für die ANSI-Typen mit der gleichen Größe, und eignen sich für das Schreiben von übertragbarem Code, der identisch verhält. auf mehreren Plattformen. Die **__int8** -Datentyp ist mit dem Typ **Char**, **__int16** ist mit dem Typ **kurze**, und **__int32**  ist mit dem Typ **Int**. Die **__int64** Typ ist mit dem Typ **long long**.

Für die Kompatibilität mit früheren Versionen **_int8**, **__int16**, **__int32**, und **__int64** sind Synonyme für **__int8** , **__int16**, **__int32**, und **__int64** , wenn Compileroption [/Za \(Sprache deaktivieren Extensions)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, dass ein __int*Xx* Parameter wird höher gestuft werden, um **Int**:

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

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Grundlegende Typen](../cpp/fundamental-types-cpp.md)<br/>
[Datentypbereiche](../cpp/data-type-ranges.md)<br/>
