---
title: Grundlegende Typen (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
dev_langs:
- C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c24ee360f1c14aa9b355f45ec1c12877efa306c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fundamental-types--c"></a>Grundlegende Typen (C++)
Grundlegende Typen in C++ werden in drei Kategorien unterteilt: integraler Typ, Gleitkommatyp und void. Von integralen Typen können ganze Zahlen verarbeitet werden. Von Gleitkommatypen können Werte angegeben werden, die möglicherweise Nachkommastellen aufweisen.  
  
 Der Typ [void](../cpp/void-cpp.md) beschreibt eine leere Menge von Werten. Es kann keine Variable vom Typ `void` angegeben werden. Dieser wird hauptsächlich verwendet, um Funktionen zu deklarieren, die keine Werte zurückgeben, oder um generische Zeiger auf nicht typisierte oder willkürlich typisierte Daten zu deklarieren. Jeder Ausdruck kann explizit konvertiert oder in den Typ `void`umgewandelt werden. Allerdings werden solche Ausdrücke auf folgende Anwendungsbereiche begrenzt:  
  
-   Eine Ausdrucksanweisung. (Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).)  
  
-   Der linke Operand des Komma-Operators. (Weitere Informationen finden Sie unter [Komma-Operator](../cpp/comma-operator.md) .)  
  
-   Der zweite oder dritte Operand des bedingten Operators (`? :`). (Weitere Informationen finden Sie unter [Ausdrücke mit dem bedingten Operator](../cpp/conditional-operator-q.md) .)  
  
 In der folgenden Tabelle werden die Einschränkungen für die Typgrößen erklärt. Diese Einschränkungen sind unabhängig von der Microsoft-Implementierung.  
  
### <a name="fundamental-types-of-the-c-language"></a>Grundlegende Typen der Programmiersprache C++  
  
|Kategorie|Typ|Inhalt|  
|--------------|----------|--------------|  
|Ganzzahlig|`char`|Der Typ `char` ist ein integraler Typ, der normalerweise Member des grundlegenden Ausführungszeichensatzes enthält. In Microsoft C++ ist dies standardmäßig ASCII.<br /><br /> Der C++-Compiler behandelt Variablen des Typs `char`, `signed` `char`und `unsigned` `char` , als würde es sich um unterschiedliche Typen handeln. Variablen des Typs `char` werden zu `int` heraufgestuft, als ob es sich standardmäßig um den Typ `signed` `char` handeln würde, es sei denn, es wird die Kompilierungsoption /J verwendet. In diesem Fall werden sie als Typ `unsigned` `char` behandelt und auf `int` ohne Vorzeichenerweiterung hochgestuft.|  
||`bool`|Der Typ `bool` ist ein integraler Typ, der entweder den Wert `true` oder `false`haben kann. Seine Größe ist nicht angegeben.|  
||`short`|Der Typ `short` `int` (oder einfach `short`) ist ein integraler Typ, der größer oder gleich der Größe des Typs `char`ist und kleiner oder gleich der Größe des Typs `int`.<br /><br /> Objekte des Typs `short` können als `signed` `short` oder `unsigned short`deklariert werden. `Signed short` ist ein Synonym für `short`.|  
||`int`|Der Typ `int` ist ein integraler Typ, der größer oder gleich der Größe des Typs `short` `int`ist und kleiner oder gleich der Größe des Typs `long`.<br /><br /> Objekte des Typs `int` können als `signed` `int` oder `unsigned` `int`deklariert werden. `Signed` `int` ist ein Synonym für `int`.|  
||`__int8`, `__int16`, `__int32`, `__int64`|Ganzzahl mit fester Größe `__int n`, wobei `n` in Bits die Größe der ganzzahligen Variablen ist. `__int8`, `__int16`, `__int32` und `__int64` sind Microsoft-spezifische Schlüsselwörter. Nicht alle Typen sind in allen Architekturen verfügbar. `(__int128` wird nicht unterstützt.)|  
||`long`|Der Typ `long` (oder `long` `int`) ist ein ganzzahliger Typ, der größer oder gleich der Größe des Typs `int`ist.<br /><br /> Objekte des Typs `long` können als `signed` `long` oder `unsigned` `long`deklariert werden. `Signed` `long` ist ein Synonym für `long`.|  
||`long` `long`|Größer als ein unsigned `long`.<br /><br /> Objekte des Typs `long long` können als `signed` `long long` oder `unsigned` `long long`deklariert werden. `signed` `long long` ist ein Synonym für `long long`.|  
||`wchar_t`, `__wchar_t`|Eine Variable des Typs `wchar_t` gibt einen Breitzeichen- oder einen Mehrbytezeichentyp an. Standardmäßig ist `wchar_t` ein systemeigener Typ. Sie können jedoch [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um `wchar_t` zu einer Typdefinition für `unsigned short`zu machen. Der Typ `__wchar_t` ist ein Microsoft-spezifisches Synonym für den systemeigenen Typ `wchar_t` .<br /><br /> Verwenden Sie das Präfix L vor einem Zeichen oder einem Zeichenliteral, um einen Breitzeichentyp festzulegen.|  
|Gleitkomma|`float`|Der Typ `float` ist der kleinste Gleitkommatyp.|  
||`double`|Der Typ `double` ist ein Gleitkommatyp, der größer oder gleich dem Typ `float`, aber kleiner oder gleich der Größe des Typs `long` `double`ist.<br /><br /> Microsoft-spezifisch: Die Darstellung von `long double` und `double` ist identisch. Allerdings sind `long double` und `double` unabhängige Typen.|  
||`long double`|Der Typ `long` `double` ist ein Gleitkommatyp, der größer als der oder gleich dem Typ `double`ist.|  
  
 **Microsoft-spezifisch**  
  
 Die folgende Tabelle enthält den Speicherumfang, der für grundlegende Typen in Microsoft C++ erforderlich ist.  
  
### <a name="sizes-of-fundamental-types"></a>Größen von grundlegenden Typen  
  
|Typ|Größe|  
|----------|----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 Byte|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 Bytes|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4 Bytes|  
|`double`, `__int64`, `long double`, `long long`|8 Bytes|  
  
 **Ende Microsoft-spezifisch**  
  
 Eine Zusammenfassung des Wertebereichs der einzelnen Typen erhalten Sie unter [Datentypbereiche](../cpp/data-type-ranges.md) .  
  
 Weitere Informationen zur Typkonvertierung finden Sie unter [Standardwertkonvertierungen](../cpp/standard-conversions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypbereiche](../cpp/data-type-ranges.md)