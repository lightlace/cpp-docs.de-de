---
title: "Grundlegende Typen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__wchar_t_cpp"
  - "long_double_cpp"
  - "unsigned"
  - "wchar_t_cpp"
  - "float_cpp"
  - "wchar_t"
  - "char"
  - "char_cpp"
  - "signed"
  - "__wchar_t"
  - "signed_cpp"
  - "short"
  - "double_cpp"
  - "int_cpp"
  - "long"
  - "__intn_cpp"
  - "short_cpp"
  - "double"
  - "unsigned_cpp"
  - "float"
  - "__intn"
  - "long_cpp"
  - "int"
  - "long_double"
  - "unsigned_int"
  - "__int8"
  - "__int8_cpp"
  - "__int16"
  - "__int16_cpp"
  - "__int32"
  - "__int32_cpp"
  - "__int64"
  - "__int64_cpp"
  - "__int128"
  - "__int128_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wchar_t-Schlüsselwort [C++]"
  - "Arithmetische Operationen [C++], Typen"
  - "char-Schlüsselwort [C++]"
  - "Datentypen [C++], void"
  - "double-Datentyp, Übersicht über Typen"
  - "float-Schlüsselwort [C++]"
  - "Gleitkommazahlen, C++-Datentypen"
  - "int-Datentyp"
  - "Integer-Datentyp, C++-Datentypen"
  - "Ganzzahlige Typen"
  - "Ganzzahlige Typen, C++"
  - "long double-Schlüsselwort [C++]"
  - "long-Schlüsselwort [C++]"
  - "long-Schlüsselwort [C++], C++-Datentypen"
  - "long long-Schlüsselwort [C++]"
  - "short-Datentyp"
  - "Typen mit Vorzeichen [C++]"
  - "Typen mit Vorzeichen [C++], Übersicht über Datentypen"
  - "Spezifizierer [C++], Typ"
  - "Speicherung [C++], Basistyp"
  - "Speichern von Typen [C++]"
  - "Typspezifizierer [C++]"
  - "Typen ohne Vorzeichen [C++]"
  - "Typen ohne Vorzeichen [C++], Übersicht über Datentypen"
  - "void-Schlüsselwort [C++]"
  - "wchar_t-Schlüsselwort [C++]"
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# Grundlegende Typen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Grundlegende Typen in C\+\+ werden in drei Kategorien unterteilt: integraler Typ, Gleitkommatyp und void. Von integralen Typen können ganze Zahlen verarbeitet werden. Von Gleitkommatypen können Werte angegeben werden, die möglicherweise Nachkommastellen aufweisen.  
  
 Der Typ [void](../cpp/void-cpp.md) beschreibt eine leere Menge von Werten. Es kann keine Variable vom Typ `void` angegeben werden. Dieser wird hauptsächlich verwendet, um Funktionen zu deklarieren, die keine Werte zurückgeben, oder um generische Zeiger auf nicht typisierte oder willkürlich typisierte Daten zu deklarieren. Jeder Ausdruck kann explizit konvertiert oder in den Typ `void` umgewandelt werden. Allerdings werden solche Ausdrücke auf folgende Anwendungsbereiche begrenzt:  
  
-   Eine Ausdrucksanweisung. \(Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).\)  
  
-   Der linke Operand des Komma\-Operators. \(Weitere Informationen finden Sie unter [Komma\-Operator](../cpp/comma-operator.md).\)  
  
-   Der zweite oder dritte Operand des bedingten Operators \(`? :`\). \(Weitere Informationen finden Sie unter [Ausdrücke mit dem bedingten Operator](../cpp/conditional-operator-q.md) .\)  
  
 In der folgenden Tabelle werden die Einschränkungen für die Typgrößen erklärt. Diese Einschränkungen sind unabhängig von der Microsoft\-Implementierung.  
  
### Grundlegende Typen der Programmiersprache C\+\+  
  
|Kategorie|Typ|Inhalt|  
|---------------|---------|------------|  
|Ganzzahlig|`char`|Der Typ `char` ist ein integraler Typ, der normalerweise Member des grundlegenden Ausführungszeichensatzes enthält. In Microsoft C\+\+ ist dies standardmäßig ASCII.<br /><br /> Der C\+\+\-Compiler behandelt Variablen des Typs `char`, `signed` `char` und `unsigned` `char`, als würde es sich um unterschiedliche Typen handeln. Variablen des Typs `char` werden zu `int` heraufgestuft, als ob es sich standardmäßig um den Typ `signed` `char` handeln würde, es sei denn, es wird die Kompilierungsoption \/J verwendet. In diesem Fall werden sie als Typ `unsigned` `char` behandelt und auf `int` ohne Vorzeichenerweiterung hochgestuft.|  
||`bool`|Der Typ `bool` ist ein integraler Typ, der entweder den Wert `true` oder `false` haben kann. Seine Größe ist nicht angegeben.|  
||`short`|Der Typ `short` `int` \(oder einfach `short`\) ist ein integraler Typ, der größer oder gleich der Größe des Typs `char` ist und kleiner oder gleich der Größe des Typs `int`.<br /><br /> Objekte des Typs `short` können als `signed` `short` oder `unsigned short` deklariert werden.`Signed short` ist ein Synonym für `short`.|  
||`int`|Der Typ `int` ist ein integraler Typ, der größer oder gleich der Größe des Typs `short` `int` ist und kleiner oder gleich der Größe des Typs `long`.<br /><br /> Objekte des Typs `int` können als `signed` `int` oder `unsigned` `int` deklariert werden.`Signed` `int` ist ein Synonym für `int`.|  
||`__int8`, `__int16`, `__int32`, `__int64`, `__int128`|Ganzzahl mit fester Größe `__int``n`, wobei `n` in Bits die Größe der ganzzahligen Variablen ist. \(`__int8`, `__int16`, `__int32`, `__int64` und `__int128` sind Microsoft\-spezifische Schlüsselwörter. Nicht alle Typen sind auf alle Architekturen verfügbar.\)|  
||`long`|Der Typ `long` \(oder `long` `int`\) ist ein ganzzahliger Typ, der größer oder gleich der Größe des Typs `int` ist.<br /><br /> Objekte des Typs `long` können als `signed` `long` oder `unsigned` `long` deklariert werden.`Signed` `long` ist ein Synonym für `long`.|  
||`long` `long`|Größer als ein unsigned `long`.<br /><br /> Objekte des Typs `long long` können als `signed` `long long` oder `unsigned` `long long` deklariert werden.`Signed` `long long` ist ein Synonym für `long long`.|  
||`wchar_t`, `__wchar_t`|Eine Variable des Typs `wchar_t` gibt einen Breitzeichen\- oder einen Mehrbytezeichentyp an. Standardmäßig ist `wchar_t` ein systemeigener Typ. Sie können jedoch [\/Zc:wchar\_t\-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um `wchar_t` zu einer Typdefinition für `unsigned short` zu machen. Der Typ `__wchar_t` ist ein Microsoft\-spezifisches Synonym für den systemeigenen Typ `wchar_t`.<br /><br /> Verwenden Sie das Präfix L vor einem Zeichen oder einem Zeichenliteral, um einen Breitzeichentyp festzulegen.|  
|Gleitkomma|`float`|Der Typ `float` ist der kleinste Gleitkommatyp.|  
||`double`|Der Typ `double` ist ein Gleitkommatyp, der größer oder gleich dem Typ `float`, aber kleiner oder gleich der Größe des Typs `long` `double` ist.<br /><br /> Microsoft\-spezifisch: Die Darstellung von `long double` und `double` ist identisch. Allerdings sind `long double` und `double` unabhängige Typen.|  
||`long double`|Der Typ `long` `double` ist ein Gleitkommatyp, der größer als der oder gleich dem Typ `double` ist.|  
  
 **Microsoft\-spezifisch**  
  
 Die folgende Tabelle enthält den Speicherumfang, der für grundlegende Typen in Microsoft C\+\+ erforderlich ist.  
  
### Größen von grundlegenden Typen  
  
|Typ|Größe|  
|---------|-----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 Byte|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 Bytes|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4 Bytes|  
|`double`, `__int64`, `long double`, `long long`|8 Bytes|  
|`__int128`|16 Bytes|  
  
 **Ende Microsoft\-spezifisch**  
  
 Eine Zusammenfassung des Wertebereichs der einzelnen Typen erhalten Sie unter [Datentypbereiche](../cpp/data-type-ranges.md).  
  
 Weitere Informationen zur Typkonvertierung finden Sie unter [Standardwertkonvertierungen](../cpp/standard-conversions.md).  
  
## Siehe auch  
 [Datentypbereiche](../cpp/data-type-ranges.md)