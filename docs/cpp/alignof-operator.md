---
title: __alignof-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7ab2eb5f33db2a62e745756971ee29f84c25c8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408825"
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
  
 Weitere Informationen über das Ändern der Ausrichtung finden Sie unter:  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md) (X64 bestimmte)  
  
 Weitere Informationen zu den Unterschieden bei der Ausrichtung im Code für x86 und x64 finden Sie unter:  
  
-   [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)