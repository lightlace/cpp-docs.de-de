---
title: Typen- und Variablengrößen in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- length
- Type
dev_langs:
- C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3466158c507e618e701df5aed35db7e5814abe52
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Typen- und Variablengrößen in der Inlineassembly
**Microsoft-spezifisch**  
  
 Die **Länge**, **Größe**, und **Typ** Operatoren haben eine begrenzte Bedeutung in der Inlineassembly. Nicht verwendet werden alle mit der `DUP` Operator (da Sie Daten mit MASM-Direktiven und Operatoren definieren können). Jedoch können Sie Sie verwenden, um die Größe von C- oder C++-Variablen oder Typen zu ermitteln:  
  
-   Die **Länge** Operator kann die Anzahl der Elemente in einem Array zurückgeben. Es gibt den Wert 1 für nicht-arrayattribute Variablen zurück.  
  
-   Die **Größe** Operator kann die Größe des eine C- oder C++-Variable zurückgeben. Eine Variable Größe ist das Produkt der **Länge** und **Typ**.  
  
-   Die **Typ** Operator kann die Größe des eine C- oder C++-Typ oder eine Variable zurückgeben. Wenn die Variable ein Array ist **Typ** gibt die Größe der ein einzelnes Element des Arrays zurück.  
  
 Angenommen, wenn das Programm ein 8-Element muss `int` Array  
  
```  
int arr[8];  
```  
  
 die folgenden Ausdrücke für C- und Assembly ergeben, die Größe des `arr` und die zugehörigen Elemente.  
  
|__asm|C|Größe|  
|-------------|-------|----------|  
|**Länge** Arr|`sizeof`(Arr) /`sizeof`(arr[0])|8|  
|**Größe** Arr|`sizeof`(Arr)|32|  
|**Typ** Arr|`sizeof`(arr[0])|4|  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)