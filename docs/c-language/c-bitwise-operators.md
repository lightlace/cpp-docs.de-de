---
title: Bitweise C-Operatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- '| operator, bitwise operators'
- bitwise operators, Visual C
- bitwise operators
- operators [C], bitwise
- ^ operator, bitwise operators
- AND operator
- ampersand operator (&)
- ^ operator
- '& operator, bitwise operators'
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 620177616e8b60d910d064d7c345633ac5155020
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-bitwise-operators"></a>C-Operatoren zur Bitmanipulation
Die bitweisen Operatoren führen bitweise AND (**&**)-, bitweise exklusive OR (**^**)- und bitweise inklusive OR(**&#124;**)-Operationen durch.  
  
 **Syntax**  
  
 *AND-expression*:  
 *equality-expression*  
  
 *AND-expression*  **&**  *equality-expression*  
  
 *exclusive-OR-expression*:  
 *AND-expression*  
  
 *exclusive-OR-expression*  **^**  *AND-expression*  
  
 *inclusive-OR-expression*:  
 *exclusive-OR-expression*  
  
 *inclusive-OR-expression* &#124; *exclusive-OR-expression*  
  
 Die Operanden für bitweise Operatoren müssen Ganzzahltypen aufweisen, aber ihre Typen können unterschiedlich sein. Diese Operatoren führen die üblichen arithmetischen Konvertierungen aus. Der Typ des Ergebnisses ist der Typ der Operanden nach der Konvertierung.  
  
 Die bitweisen C-Operatoren sind im Folgenden beschrieben:  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|**&**|Der bitweise AND-Operator vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn beide Bits 1 sind, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.|  
|**^**|Der bitweise exklusive OR-Operator vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn ein Bit 0 (null) und das andere Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.|  
|**&#124;**|Der bitweise inklusive OR-Operator vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn jedes Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.|  
  
## <a name="examples"></a>Beispiele  
 Diese Deklarationen werden für die folgenden drei Beispiele verwendet:  
  
```  
short i = 0xAB00;  
short j = 0xABCD;  
short n;  
  
n = i & j;  
```  
  
 Das Ergebnis, das `n` in diesem ersten Beispiel zugewiesen wird, entspricht `i` (0xAB00 hexadezimal).  
  
```  
n = i | j;  
  
n = i ^ j;  
```  
  
 Der bitweise inklusive OR-Operator im zweiten Beispiel ergibt den Wert 0xABCD (hexadezimal), während der bitweise exklusive OR-Operator im dritten Beispiel 0xCD (hexadezimal) zurückgibt.  
  
 **Microsoft-spezifisch**  
  
 Die Ergebnisse der bitweisen Operationen für ganze Zahlen mit Vorzeichen hängen gemäß ANSI C-Standard von der jeweiligen Implementierung ab. Für den Microsoft C-Compiler funktionieren bitweise Operationen für ganze Zahlen mit Vorzeichen genauso wie bitweise Operationen für ganze Zahlen ohne Vorzeichen. So kann beispielsweise `-16 & 99` binär ausgedrückt werden als  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Das Ergebnis der bitweisen AND-Operation ist 96 dezimal.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Bitweiser AND-Operator: &](../cpp/bitwise-and-operator-amp.md)   
 [Bitweiser exklusiver OR-Operator: ^](../cpp/bitwise-exclusive-or-operator-hat.md)   
 [Bitweiser inklusiver OR-Operator: &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)
