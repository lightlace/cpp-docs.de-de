---
title: "__alignof-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__alignof"
  - "alignof"
  - "alignas"
  - "__alignof_cpp"
  - "alignof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__alignof-Schlüsselwort [C++]"
  - "alignas"
  - "Ausrichtung von Strukturen"
  - "alignof"
  - "Typen [C++], Ausrichtungsanforderungen"
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# __alignof-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C \+\+ 11 stellt die `alignof` Operator, der die Ausrichtung des angegebenen Typs in Bytes zurückgibt.  Zur maximalen Portabilität sollten Sie den „alignof“ des Operators statt des Microsoft\-spezifischen „\_\_alignof“\-Operators verwenden.  
  
 **Microsoft\-spezifisch**  
  
 Gibt einen Wert vom Typ **size\_t** zurück, der der Ausrichtungsanforderung des Typs entspricht.  
  
## Syntax  
  
```  
  
        __alignof(   
   type    
)  
```  
  
## Hinweise  
 Zum Beispiel:  
  
|Ausdruck|Wert|  
|--------------|----------|  
|**\_\_alignof \(char\)**|1|  
|**\_\_alignof \(short\)**|2|  
|**\_\_alignof \(int\)**|4|  
|**\_\_alignof \(\_\_int64\)**|8|  
|**\_\_alignof \(float\)**|4|  
|**\_\_alignof \(double\)**|8|  
|**\_\_alignof \(char\*\)**|4|  
  
 Der `__alignof`\-Wert entspricht dem `sizeof`\-Wert für Basistypen.  Betrachten Sie jedoch das Beispiel:  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 In diesem Fall ist der `__alignof`\-Wert die Ausrichtungsanforderung des größten Elements in der Struktur.  
  
 Entsprechend gilt:  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` ist gleich `32`.  
  
 Eine Verwendung für `__alignof` wäre als Parameter für eine Ihrer Speicherbelegungsroutinen.  Beispielsweise könnten Sie angesichts der folgenden definierten Struktur `S` eine Speicherbelegungsroutine mit dem Namen `aligned_malloc` aufrufen, um einen bestimmten Grenzwert mit Speicher zu belegen.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Weitere Informationen über das Ändern der Ausrichtung finden Sie unter:  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [\/Zp \(Ausrichten des Strukturmembers\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md) \(x64\-spezifisch\)  
  
 Weitere Informationen zu den Unterschieden bei der Ausrichtung im Code für x86 und x64 finden Sie unter:  
  
-   [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)