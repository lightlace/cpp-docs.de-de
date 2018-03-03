---
title: C-Zuweisungsoperatoren | Microsoft-Dokumentation
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
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c839538b94ff8f80eabed98dbaf16e4009d3e500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-assignment-operators"></a>C-Zuweisungsoperatoren
Eine Zuweisungsvorgang weist den Wert des rechten Operanden dem Speicherort zu, der vom linken Operanden benannt wird. Deshalb muss der linke Operand eines Zuweisungsvorgangs ein änderbarer l-Wert sein. Nach der Zuweisung hat ein Zuweisungsausdruck den Wert des linken Operanden, ist jedoch kein L-Wert.  
  
 **Syntax**  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: Einer von  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 Die Zuweisungsoperatoren in C können Werte in einem einzelnen Vorgang transformieren und zuweisen. C stellt die folgenden Zuweisungsoperatoren bereit:  
  
|Operator|Vorgang ausgeführt|  
|--------------|-------------------------|  
|**=**|Einfache Zuweisung|  
|**\*=**|Multiplikationszuweisung|  
|`/=`|Divisionszuweisung|  
|`%=`|Restzuweisung|  
|`+=`|Additionszuweisung|  
|**-=**|Subtraktionszuweisung|  
|**<\<=**|Linksschiebezuweisung|  
|**>>=**|Rechtsschiebezuweisung|  
|**&=**|Bitweise AND-Zuweisung|  
|`^=`|Bitweise exklusive OR-Zuweisung|  
|`&#124;=`|Bitweise inklusive OR-Zuweisung|  
  
 In der Zuweisung wird der Typ des rechten Werts in den Typ des linken Werts konvertiert, und der Wert wird im linken Operanden gespeichert, nachdem die Zuweisung stattgefunden hat. Der linke Operand darf kein Array, keine Funktion und keine Konstante sein. Der bestimmte Konvertierungspfad, der von den beiden Typen abhängt, wird ausführlich in [Typkonvertierungen](../c-language/type-conversions-c.md) erläutert.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuweisungsoperatoren](../cpp/assignment-operators.md)