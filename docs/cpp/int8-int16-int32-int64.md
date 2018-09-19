---
title: __int8, __int16, __int32, __int64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 723724a477a5cdb714aa2644e1db938d67fb7b73
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194250"
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
