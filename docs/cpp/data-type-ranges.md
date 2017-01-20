---
title: "Datentypbereiche"
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
  - "unsigned"
  - "wchar_t"
  - "char"
  - "signed"
  - "short"
  - "long"
  - "double"
  - "float"
  - "int"
  - "long_double"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "float-Schlüsselwort [C++]"
  - "char-Schlüsselwort [C++]"
  - "unsigned long"
  - "__wchar_t-Schlüsselwort [C++]"
  - "unsigned short int"
  - "enum-Schlüsselwort"
  - "unsigned char-Schlüsselwort [C++]"
  - "integer-Datentyp, Datentypbereiche"
  - "int-Datentyp"
  - "Datentypen [C++], Bereiche"
  - "unsigned int"
  - "short-Datentyp"
  - "short int-Daten"
  - "Typen mit Vorzeichen [C++], Datentypbereiche"
  - "long long-Schlüsselwort [C++]"
  - "long double-Schlüsselwort [C++]"
  - "double-Datentyp, Datentypbereiche"
  - "signed short int"
  - "unsigned short"
  - "Angepasste Ganzzahltypen"
  - "signed int"
  - "signed long int"
  - "signed char-Schlüsselwort [C++]"
  - "wchar_t-Schlüsselwort [C++]"
  - "long-Schlüsselwort [C++]"
  - "Bereiche [C++]"
  - "Typen ohne Vorzeichen [C++], Datentypbereiche"
  - "Gleitkommazahlen, Datentypbereiche"
  - "Bereiche [C++], Datentypen"
  - "long int-Schlüsselwort [C++]"
  - "unsigned long int"
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Datentypbereiche
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Von den Visual C++-32-Bit-- und 64-Bit-Compilern werden die Typen in der Tabelle weiter unten in diesem Artikel erkannt.  
  
-   `int` (`unsigned``int`)  
  
-   `__int8` (`unsigned``__int8`)  
  
-   `__int16` (`unsigned``__int16`)  
  
-   `__int32` (`unsigned``__int32`)  
  
-   `__int64` (`unsigned``__int64`)  
  
-   `short` (`unsigned``short`)  
  
-   `long` (`unsigned``long`)  
  
-   `long` `long` (`unsigned``long``long`)  
  
 Wenn der Name mit zwei Unterstrichen (`__`) beginnt, handelt es sich um einen nicht standardisierten Datentyp.  
  
 Die Bereiche, die in der folgenden Tabelle angegeben werden, sind "inclusive-inclusive".  
  
|Typname|Bytes|Andere Namen|Wertebereich|  
|---------------|-----------|-----------------|---------------------|  
|int|4|signed|–2.147.483.648 bis 2.147.483.647|  
|unsigned int|4|unsigned|0 bis 4.294.967.295|  
|__int8|1|char|–128 bis 127|  
|unsigned __int8|1|unsigned char|0 bis 255|  
|__int16|2|short, short int, signed short int|–32.768 bis 32.767|  
|unsigned __int16|2|unsigned short, unsigned short int|0 bis 65.535|  
|__int32|4|signed, signed int, int|–2.147.483.648 bis 2.147.483.647|  
|unsigned __int32|4|unsigned, unsigned int|0 bis 4.294.967.295|  
|__int64|8|long long, signed long long|–9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807|  
|unsigned __int64|8|unsigned long long|0 bis 18.446.744.073.709.551.615|  
|bool|1|Keine|false oder true|  
|char|1|Keine|–128 bis 127 (Standard)<br /><br /> 0 bis 255, falls mithilfe von [/J](../build/reference/j-default-char-type-is-unsigned.md) kompiliert|  
|char mit Vorzeichen|1|Keine|–128 bis 127|  
|unsigned char|1|Keine|0 bis 255|  
|short|2|short int, signed short int|–32.768 bis 32.767|  
|unsigned short|2|unsigned short int|0 bis 65.535|  
|long|4|long int, signed long int|–2.147.483.648 bis 2.147.483.647|  
|unsigned long|4|unsigned long int|0 bis 4.294.967.295|  
|long long|8|none (jedoch äquivalent zu __int64)|–9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807|  
|unsigned long long|8|none (jedoch äquivalent zu unsigned __int64)|0 bis 18.446.744.073.709.551.615|  
|enum|varies|Keine|Siehe [Hinweise](#bkmkRemarks) weiter unten in diesem Artikel|  
|frei verschieben|4|Keine|3.4E +/- 38 (7 Stellen)|  
|double|8|Keine|1.7E +/- 308 (15 Stellen)|  
|long double|entspricht double|Keine|entspricht double|  
|wchar_t|2|__wchar_t|0 bis 65.535|  
  
 Abhängig von der Verwendung wird durch die Variable `__wchar_t` entweder ein Breitzeichen oder ein Mehrbytezeichen angegeben. Verwenden Sie das Präfix `L` vor einem Zeichen oder einer Zeichenfolgenkonstante, um eine Breitzeichenkonstante festzulegen.  
  
 `signed` und `unsigned` sind Modifizierer, die mit jedem ganzzahligen Typ mit Ausnahme von `bool` verwendet werden können. Beachten Sie, dass `char`, `signed char` und `unsigned char` drei verschiedene Typen für Mechanismen wie Überladen und Vorlagen sind.  
  
 Die Typen `int` und `unsigned``int` haben eine Größe von vier Bytes. Der übertragbare Code sollte jedoch nicht von der Größe von `int` abhängen, da der Standard der Sprache implementierungsspezifische Werte ermöglicht.  
  
 C/C++ in Visual Studio bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Weitere Informationen finden Sie unter [__int8, \___int16, \___int32, \___int64](../cpp/int8-int16-int32-int64.md) und [Integer Limits (Integer Grenzen)](../cpp/integer-limits.md).  
  
 Weitere Informationen über Größeneinschränkungen der einzelnen Typen finden Sie unter [Fundamental Types (Grundlegende Typen)](../cpp/fundamental-types-cpp.md).  
  
 Der Bereich von Enumerationstypen variiert je nach Sprachkontext und angegebenen Compilerflags. Weitere Informationen finden Sie unter [C Enumeration Declarations (C-Enumerationsdeklarationen)](../c-language/c-enumeration-declarations.md) und [Enumerations (Enumerationen)](../cpp/enumerations-cpp.md).  
  
## Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)