---
title: Grundlegende Typen (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 7abb1efa9ca7260648574299cde454a33f84b3f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114890"
---
# <a name="fundamental-types--c"></a>Grundlegende Typen (C++)

Grundlegende Typen in C++ werden in drei Kategorien unterteilt: integraler Typ, Gleitkommatyp und void. Von integralen Typen können ganze Zahlen verarbeitet werden. Von Gleitkommatypen können Werte angegeben werden, die möglicherweise Nachkommastellen aufweisen.

Der Typ [void](../cpp/void-cpp.md) beschreibt eine leere Menge von Werten. Keine Variable vom Typ **"void"** kann angegeben werden, dient in erster Linie zum Deklarieren von Funktionen, die keine Werte zurückgeben, oder deklarieren generische Zeiger auf nicht typisierte oder willkürlich typisierte Daten. Jeder Ausdruck kann explizit konvertiert oder umgewandelt Typ **"void"**. Allerdings werden solche Ausdrücke auf folgende Anwendungsbereiche begrenzt:

- Eine Ausdrucksanweisung. (Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).)

- Der linke Operand des Komma-Operators. (Weitere Informationen finden Sie unter [Komma-Operator](../cpp/comma-operator.md) .)

- Der zweite oder dritte Operand des bedingten Operators (`? :`). (Weitere Informationen finden Sie unter [Ausdrücke mit dem bedingten Operator](../cpp/conditional-operator-q.md) .)

In der folgenden Tabelle werden die Einschränkungen für die Typgrößen erklärt. Diese Einschränkungen sind unabhängig von der Microsoft-Implementierung.

### <a name="fundamental-types-of-the-c-language"></a>Grundlegende Typen der Programmiersprache C++

|Kategorie|Typ|Inhalt|
|--------------|----------|--------------|
|Ganzzahlig|**char**|Typ **Char** ist ein integraler Typ, der normalerweise Member des grundlegenden ausführungszeichensatz enthält, ist dies standardmäßig ASCII in Microsoft C++.<br /><br /> Der C++-Compiler behandelt Variablen des Typs **Char**, **signiert Char**, und **unsigned Char** als mit unterschiedlichen Typen. Variablen vom Typ **Char** zu hochgestuft **Int** als wären sie Typ **signiert Char** standardmäßig, wenn die Kompilierungsoption/j verwendet wird. In diesem Fall werden sie als Typ behandelt **unsigned Char** und zu hochgestuft **Int** ohne vorzeichenerweiterung.|
||**bool**|Typ **"bool"** ist ein integraler Typ, der einen der beiden Werte enthalten kann **"true"** oder **"false"**. Seine Größe ist nicht angegeben.|
||**short**|Typ **short Int** (oder einfach **kurze**) ist ein integraler Typ, der größer als oder gleich der Größe des Typs **Char**, und kleiner als oder gleich der Größe des Typs **Int**.<br /><br /> Objekte des Typs **kurze** können deklariert werden, als **kurz signiert** oder **unsigned short**. **Kurz gesagt signiert** ist ein Synonym für **kurze**.|
||**int**|Typ **Int** ist ein integraler Typ, der größer als oder gleich der Größe des Typs **short Int**, und kleiner als oder gleich der Größe des Typs **lange**.<br /><br /> Objekte des Typs **Int** können deklariert werden, als **signiert Int** oder **ganze Zahl ohne Vorzeichen**. **Int signiert** ist ein Synonym für **Int**.|
||**__int8**, **__int16**, **__int32**, **__int64**|Ganzzahl mit fester Größe `__int n`, wobei `n` in Bits die Größe der ganzzahligen Variablen ist. **__int8**, **__int16**, **__int32** und **__int64** sind Microsoft-spezifische Schlüsselwörter. Nicht alle Typen sind in allen Architekturen verfügbar. (**__int128** wird nicht unterstützt.)|
||**long**|Typ **lange** (oder **long Int**) ist ein integraler Typ, der größer als oder gleich der Größe des Typs **Int**.<br /><br /> Objekte des Typs **lange** können deklariert werden, als **lange signiert** oder **unsigned long**. **Lange signiert** ist ein Synonym für **lange**.|
||**langes long**|Größer als ein unsigned **lange**.<br /><br /> Objekte des Typs **long long** können deklariert werden, als **long long signiert** oder **long long ohne Vorzeichen**. **long long signiert** ist ein Synonym für **long long**.|
||**"wchar_t"**, **"__wchar_t"**|Eine Variable vom Typ **"wchar_t"** kennzeichnet einen Breitzeichen oder Multibytezeichen Zeichentyp. In der Standardeinstellung **"wchar_t"** ist ein systemeigener Typ, aber Sie können [/Zc:](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) vornehmen **"wchar_t"** eine Typedef für **unsigned short**. Die **__wchar_t** Typ ist ein Microsoft-spezifisches Synonym für den systemeigenen **"wchar_t"** Typ.<br /><br /> Verwenden Sie das Präfix L vor einem Zeichen oder einem Zeichenliteral, um einen Breitzeichentyp festzulegen.|
|Gleitkomma|**float**|Typ **"float"** ist der kleinste Gleitkommatyp Punkttyp.|
||**double**|Typ **doppelte** ist ein Gleitkommatyp, der größer als oder gleich dem Typ **"float"**, aber kleiner oder gleich der Größe des Typs **long double**.<br /><br /> Microsoft-spezifisch: die Darstellung der **long double** und **doppelte** identisch ist. Allerdings **long double** und **doppelte** sind separate Projektionstypen und.|
||**long double**|Typ **long double** ist ein Gleitkommatyp, der größer als oder gleich dem Typ **doppelte**.|

**Microsoft-spezifisch**

Die folgende Tabelle enthält den Speicherumfang, der für grundlegende Typen in Microsoft C++ erforderlich ist.

### <a name="sizes-of-fundamental-types"></a>Größen von grundlegenden Typen

|Typ|Größe|
|----------|----------|
|**"bool"**, **Char**, **unsigned Char**, **signiert Char**, **__int8**|1 Byte|
|**__int16**, **kurze**, **unsigned short**, **"wchar_t"**, **"__wchar_t"**|2 Bytes|
|**"float"**, **__int32**, **Int**, **ganze Zahl ohne Vorzeichen**, **lange**, **unsigned long**|4 Bytes|
|**doppelte**, **__int64**, **long double**, **long long**|8 Bytes|

**Ende Microsoft-spezifisch**

Eine Zusammenfassung des Wertebereichs der einzelnen Typen erhalten Sie unter [Datentypbereiche](../cpp/data-type-ranges.md) .

Weitere Informationen zur Typkonvertierung finden Sie unter [Standardwertkonvertierungen](../cpp/standard-conversions.md).

## <a name="see-also"></a>Siehe auch

[Datentypbereiche](../cpp/data-type-ranges.md)