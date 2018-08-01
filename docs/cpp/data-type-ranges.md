---
title: Datentypbereiche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d55a2102299957a40cd9f742f91868ee2b5b849b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407675"
---
# <a name="data-type-ranges"></a>Datentypbereiche
Von den Visual C++-32-Bit-- und 64-Bit-Compilern werden die Typen in der Tabelle weiter unten in diesem Artikel erkannt.  
  
-   `int` (`unsigned int`)  
  
-   `__int8` (`unsigned __int8`)  
  
-   `__int16` (`unsigned __int16`)  
  
-   `__int32` (`unsigned __int32`)  
  
-   `__int64` (`unsigned __int64`)  
  
-   `short` (`unsigned short`)  
  
-   `long` (`unsigned long`)  
  
-   `long` `long` (`unsigned long long`)  
  
 Wenn der Name mit zwei Unterstrichen (`__`) beginnt, handelt es sich um einen nicht standardisierten Datentyp.  
  
 Die Bereiche, die in der folgenden Tabelle angegeben werden, sind "inclusive-inclusive".  
  
|Typname|Bytes|Andere Namen|Wertebereich|  
|---------------|-----------|-----------------|---------------------|  
|**int**|4|**signed**|-2,147,483,648 bis 2,147,483,647|  
|**unsigned int**|4|**unsigned**|0 bis 4.294.967.295|  
|**__int8**|1|**char**|–128 bis 127|  
|**nicht signierte __int8**|1|**unsigned char**|0 bis 255|  
|**__int16**|2|**kurze**, **short Int**, **signiert short Int**|–32.768 bis 32.767|  
|**nicht signierte __int16**|2|**unsigned short**, **kurze ganze Zahl ohne Vorzeichen**|0 bis 65.535|  
|**__int32**|4|**signiert**, **signiert Int**, **Int**|-2,147,483,648 bis 2,147,483,647|  
|**nicht signierte __int32**|4|**nicht signierte**, **ganze Zahl ohne Vorzeichen**|0 bis 4.294.967.295|  
|**__int64**|8|**long long**, **signiert long long**|-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807|  
|**__int64 ohne Vorzeichen**|8|**long long ohne Vorzeichen**|0 bis 18.446.744.073.709.551.615|  
|**bool**|1|Keine|**"false"** oder **"true"**|  
|**char**|1|Keine|– 128 bis 127 standardmäßig<br /><br /> 0 bis 255, falls mithilfe von [/J](../build/reference/j-default-char-type-is-unsigned.md)kompiliert|  
|**Char mit Vorzeichen**|1|Keine|–128 bis 127|  
|**unsigned char**|1|Keine|0 bis 255|  
|**short**|2|**short Int**, **signiert short Int**|–32.768 bis 32.767|  
|**unsigned short**|2|**unsigned short int**|0 bis 65.535|  
|**long**|4|**Long Int**, **signiert long Int**|-2,147,483,648 bis 2,147,483,647|  
|**unsigned long**|4|**unsigned long int**|0 bis 4.294.967.295|  
|**langes long**|8|None (jedoch äquivalent zu **__int64**)|-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807|  
|**long long ohne Vorzeichen**|8|None (jedoch äquivalent zu **__int64 ohne Vorzeichen**)|0 bis 18.446.744.073.709.551.615|  
|**enum**|varies|Keine| |  
|**float**|4|Keine|3.4E +/- 38 (7 Stellen)|  
|**double**|8|Keine|1.7E +/- 308 (15 Stellen)|  
|**long double**|identisch mit **double**|Keine|Identisch mit **double**|  
|**wchar_t**|2|**"__wchar_t"**|0 bis 65.535|  
  
 Je nachdem wie diese verwendet werden, eine Variable vom **__wchar_t** weist eine Breitzeichen-Typ oder eine Multibyte-Zeichentyp. Verwenden Sie das Präfix `L` vor einem Zeichen oder einer Zeichenfolgenkonstante, um eine Breitzeichenkonstante festzulegen.  
  
 **signiert** und **ohne Vorzeichen** sind Modifizierer, mit denen Sie mit jedem ganzzahligen Typ außer **"bool"**. Beachten Sie, dass **Char**, **signiert Char**, und **unsigned Char** sind drei separate Typen für Mechanismen wie überladen und Vorlagen.  
  
 Die **Int** und **ganze Zahl ohne Vorzeichen** Typen haben eine Größe von 4 Bytes. Übertragbarem Code sollte jedoch nicht abhängig, auf die Größe des **Int** da standard die Sprache implementierungsspezifische sein kann.  
  
 C/C++ in Visual Studio bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Weitere Informationen finden Sie unter [__int8, \___int16, \___int32, \___int64](../cpp/int8-int16-int32-int64.md) und [Integer Limits (Integer Grenzen)](../cpp/integer-limits.md).  
  
 Weitere Informationen über Größeneinschränkungen der einzelnen Typen finden Sie unter [Fundamental Types (Grundlegende Typen)](../cpp/fundamental-types-cpp.md).  
  
 Der Bereich von Enumerationstypen variiert je nach Sprachkontext und angegebenen Compilerflags. Weitere Informationen finden Sie unter [C Enumeration Declarations (C-Enumerationsdeklarationen)](../c-language/c-enumeration-declarations.md) und [Enumerations (Enumerationen)](../cpp/enumerations-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)