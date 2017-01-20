---
title: "__int8, __int16, __int32, __int64"
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
  - "__int8_cpp"
  - "__int64"
  - "__int8"
  - "__int16"
  - "__int16_cpp"
  - "__int64_cpp"
  - "__int32_cpp"
  - "__int32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__int16-Schlüsselwort [C++]"
  - "__int32-Schlüsselwort [C++]"
  - "__int64-Schlüsselwort [C++]"
  - "__int8-Schlüsselwort [C++]"
  - "integer-Datentyp, Ganzzahltypen in C++"
  - "Ganzzahlentypen [C++]"
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# __int8, __int16, __int32, __int64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Microsoft C\/C\+\+ bietet Unterstützung für ganzzahlige Typen mit angegebener Größe.  Sie können ganzzahlige Variablen mit 8, 16, 32 oder 64 Bit deklarieren, indem Sie den **\_\_int***n*\-Typspezifizierer verwenden, wobei *n* für 8, 16, 32 oder 64 steht.  
  
 Im folgenden Beispiel wird eine Variable für jeden dieser Typen von ganzen Zahlen mit angegebener Größe deklariert:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Die Typen `__int8`, `__int16` und `__int32` sind Synonyme für die ANSI\-Typen, die die gleiche Größe aufweisen, und sind beim Schreiben von portablem Code nützlich, der sich plattformübergreifend identisch verhält.  Der `__int8`\-Datentyp wird mit Typ `char` synonym verwendet, `__int16` wird mit Typ **short** synonym verwendet, und `__int32` wird mit Typ `int` synonym verwendet.  Der Typ `__int64` hat keine ANSI\-Entsprechung.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, dass ein \_\_int*xx*\-Parameter zu `int` hochgestuft wird:  
  
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
  
  **func**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)   
 [Datentypbereiche](../cpp/data-type-ranges.md)