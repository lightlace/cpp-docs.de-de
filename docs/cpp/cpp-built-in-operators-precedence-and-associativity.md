---
title: "Integrierte C++-Operatoren, Rangfolge und Assoziativität | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6c45b0d3ff2aaee6763b73949727dcde5ee744bc
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Integrierte C++-Operatoren, Rangfolge und Assoziativität
Die Sprache C++ umfasst alle C-Operatoren und fügt mehrere neue Operatoren hinzu. Operatoren legen eine Bewertung fest, die an einem oder mehreren Operanden auszuführen ist.  
  
 Die Operatorrangfolge legt die Reihenfolge von Vorgängen in Ausdrücken fest, die mehr als einen Operator enthalten. Die Assoziativität von Operatoren gibt an, ob in einem Ausdruck, der mehrere Operatoren mit der selben Rangfolge enthält, ein Operand mit dem auf der linken oder dem auf der rechten Seite gruppiert wird. Die folgende Tabelle zeigt die Rangfolge und Assoziativität von C++-Operatoren (in absteigender Rangfolge). Operatoren mit derselben Rangfolgenzahl haben die gleiche Rangfolge, es sei denn, es wird eine andere Beziehung explizit durch Klammern erzwungen.  
  
### <a name="c-operator-precedence-and-associativity"></a>C++-Operatorrangfolge und Assoziativität  
  
|Operatorbeschreibung|Operator|  
|--------------------------|--------------|  
|`Group 1 precedence, no associativity`|  
|[Bereichsauflösung](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[Memberauswahl (Objekt oder Zeiger)](../cpp/member-access-operators-dot-and.md)|`. or ->`|  
|[Arrayfeldindex](../cpp/subscript-operator.md)|`[ ]`|  
|[Funktionsaufruf](../cpp/function-call-operator-parens.md)|`( )`|  
|[Postfix-Inkrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Postfixdekrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Typname](../cpp/typeid-operator.md)|`typeid( )`|  
|[Konstantentypkonvertierung](../cpp/const-cast-operator.md)|`const_cast`|  
|[Dynamische typkonvertierung](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[Neu interpretierte typkonvertierung](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[Statische typkonvertierung](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[Größe des Objekts oder Typs](../cpp/sizeof-operator.md)|`sizeof`|  
|[Präfixinkrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Präfixdekrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Einerkomplement](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[Logisches not](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[Unäre negation](../cpp/unary-plus-and-negation-operators-plus-and.md)|`-`|  
|[Unäres plus](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[Adresse des](../cpp/lvalue-reference-declarator-amp.md)|`&`|  
|[Dereferenzierung](../cpp/indirection-operator-star.md)|`*`|  
|[Objekt erstellen](../cpp/new-operator-cpp.md)|`new`|  
|[Objekt zerstören](../cpp/delete-operator-cpp.md)|`delete`|  
|[Typumwandlung](../cpp/cast-operator-parens.md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[Pointer-to-Member (Objekte oder Zeiger)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or ->*`|  
|`Group 5 precedence, left to right associativity`|  
|[Multiplikation](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[Division](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[Modulo](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[Hinzufügen](../cpp/additive-operators-plus-and.md)|`+`|  
|[Subtraktion](../cpp/additive-operators-plus-and.md)|`-`|  
|`Group 7 precedence, left to right associativity`|  
|[Nach links verschieben](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`<<`|  
|[Nach rechts verschieben](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[Kleiner als](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[Größer als](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[Kleiner als oder gleich](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[Größer als oder gleich](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[Gleichheit](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[Ungleichheitsoperator](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[Bitweises AND](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[Bitweises exklusives OR](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[Bitweises inklusives OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[Logisches AND](../cpp/logical-and-operator-amp-amp.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[Logisches OR](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[Bedingte](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[Zuweisung](../cpp/assignment-operators.md)|`=`|  
|[Multiplikationszuweisung](../cpp/assignment-operators.md)|`*=`|  
|[Divisionszuweisung](../cpp/assignment-operators.md)|`/=`|  
|[Modulozuweisung](../cpp/assignment-operators.md)|`%=`|  
|[Additionszuweisung](../cpp/assignment-operators.md)|`+=`|  
|[Subtraktionszuweisung](../cpp/assignment-operators.md)|`-=`|  
|[Linksschiebezuweisung](../cpp/assignment-operators.md)|`<<=`|  
|[Rechtsschiebezuweisung](../cpp/assignment-operators.md)|`>>=`|  
|[Bitweise AND-Zuweisung](../cpp/assignment-operators.md)|`&=`|  
|[Bitweise inklusive OR-Zuweisung](../cpp/assignment-operators.md)|`&#124;=`|  
|[Bitweise exklusive OR-Zuweisung](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[Ausdruck auslösen](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[Durch Trennzeichen](../cpp/comma-operator.md)|`,`|  
  
## <a name="see-also"></a>Siehe auch  
[Operatorüberladung](operator-overloading.md)



