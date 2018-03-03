---
title: __int8, __int16, __int32, __int64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 957e2483d61855c442780440ccf87441f00cb1c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Microsoft C/C++ bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Sie können die 8, 16, 32 oder 64-Bit-Ganzzahl-Variablen deklarieren, indem die **__int**  *n*  Typspezifizierer verwenden, wobei  *n*  ist 8, 16, 32 oder 64.  
  
 Im folgenden Beispiel wird eine Variable für jeden dieser Typen von ganzen Zahlen mit angegebener Größe deklariert:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Die Typen `__int8`, `__int16` und `__int32` sind Synonyme für die ANSI-Typen, die die gleiche Größe aufweisen, und sind beim Schreiben von portablem Code nützlich, der sich plattformübergreifend identisch verhält. Die `__int8` -Datentyp ist mit dem Typ `char`, `__int16` ist mit dem Typ **kurze**, und `__int32` ist mit dem Typ `int`. Die `__int64` Typ wird mit dem Typ `long long`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, dass ein __int*Xx* Parameter höhergestuft, `int`:  
  
```  
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
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)   
 [Datentypbereiche](../cpp/data-type-ranges.md)