---
title: "Unärer Plus- und Negationsoperatoren: + und - | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs: C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12aba6e13f10d05c8559439427d2d28bcdad089d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unary-plus-and-negation-operators--and--"></a>Unärer Plus- und Negationsoperatoren: + und -
## <a name="syntax"></a>Syntax  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+-Operator  
 Das Ergebnis des unären plus -Operators (**+**) ist der Wert seines Operanden. Der Operand für den unären Plus-Operator muss ein arithmetischer Typ sein.  
  
 Ganzzahlige Erweiterung wird für ganzzahlige Operanden ausgeführt. Der resultierende Typ ist der Typ, in den der Operand heraufgestuft wird. Daher resultiert der Ausdruck `+ch`, in dem `ch` vom Typ `char` ist, im Typ `int`. Der Wert bleibt unverändert. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen zur Durchführung der heraufstufung.  
  
## <a name="--operator"></a>--Operator  
 Der unäre Negationsoperator (**-**) erzeugt den negativen Wert seines Operanden. Der Operand für den unären Negationsoperator muss ein arithmetischer Typ sein.  
  
 Ganzzahlige Erweiterung wird für ganzzahlige Operanden durchgeführt, und der resultierende Typ ist der Typ, auf den der Operand erweitert wird. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen zur Ausführung der heraufstufung.  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Eine unäre Negation von Mengen ohne Vorzeichen wird ausgeführt, indem der Wert des Operanden von 2^n subtrahiert wird, wobei n die Anzahl von Bits in einem Objekt des angegebenen vorzeichenlosen Typs ist. (Microsoft C++ wird auf Prozessoren ausgeführt, die Zweierkomplementarithmetik verwenden. Bei anderen Prozessoren kann der Algorithmus für Negationen abweichen.)  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)