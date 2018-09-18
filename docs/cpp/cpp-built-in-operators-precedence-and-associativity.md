---
title: C++-Built-Operatoren, Rangfolge und Assoziativität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b40e5ab6cac64edbfdb5ab93c6864d0eacb9e63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073101"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++-Built-Operatoren, Rangfolge und Assoziativität

Die Sprache C++ umfasst alle C-Operatoren und fügt mehrere neue Operatoren hinzu. Operatoren legen eine Bewertung fest, die an einem oder mehreren Operanden auszuführen ist.

Operator *Rangfolge* gibt die Reihenfolge der Vorgänge in Ausdrücken, die mehr als einen Operator enthalten. Operator *Assoziativität* gibt an, ob in einem Ausdruck, der mehrere Operatoren mit gleicher Rangfolge enthält, ein Operand mit dem auf der linken Seite oder auf der rechten Seite gruppiert ist. Die folgende Tabelle zeigt die Rangfolge und Assoziativität von C++-Operatoren (in absteigender Rangfolge). Operatoren mit derselben Rangfolgenzahl haben die gleiche Rangfolge, es sei denn, es wird eine andere Beziehung explizit durch Klammern erzwungen.

### <a name="c-operator-precedence-and-associativity"></a>C++-Operatorrangfolge und Assoziativität

|Operatorbeschreibung|Operator|
|--------------------------|--------------|
|**Gruppe 1 Rangfolge, die keine Assoziativität**|
|[Bereichsauflösung](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Gruppe 2-Priorität, von links nach rechts Assoziativität**|
|[Memberauswahl (Objekt oder Zeiger)](../cpp/member-access-operators-dot-and.md)|[. oder der->](../cpp/member-access-operators-dot-and.md)|
|[Array-subscript](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[Funktionsaufruf](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Postfix-Inkrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Postfixdekrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Typnamen](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Konstantentypkonvertierung](../cpp/const-cast-operator.md)|[const_cast-Operator](../cpp/const-cast-operator.md)|
|[Dynamische typkonvertierung](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Neu interpretierte typkonvertierung](../cpp/reinterpret-cast-operator.md)|["reinterpret_cast"](../cpp/reinterpret-cast-operator.md)|
|[Statische typkonvertierung](../cpp/static-cast-operator.md)|[static_cast-Operator](../cpp/static-cast-operator.md)|
|**Gruppe 3 Vorrang, rechts-nach-links-Assoziativität**|
|[Größe des Objekts oder Typs](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Präfixinkrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Präfixdekrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Einerkomplement](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Logisches not](../cpp/logical-negation-operator-exclpt.md)|[\!](../cpp/logical-negation-operator-exclpt.md)|
|[Unäre Negation](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Unäres plus](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Adresse des](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Dereferenzierung](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Objekt erstellen](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Objekt zerstören](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Typumwandlung](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Gruppe 4 Rangfolge von links nach rechts Assoziativität**|
|[Pointer-to-Member (Objekte oder Zeiger)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; oder der->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Gruppe 5 Rangfolge von links nach rechts Assoziativität**|
|[Multiplikation](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Division](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Modulo](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Gruppe 6 Rangfolge von links nach rechts Assoziativität**|
|[Addition](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Subtraktion](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Gruppe 7 Rangfolge von links nach rechts Assoziativität**|
|[Nach links verschieben](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Nach rechts verschieben](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Gruppe 8 Rangfolge von links nach rechts Assoziativität**|
|[Kleiner als](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Größer als](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Kleiner gleich](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Größer gleich](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Gruppe 9 Vorrang, von links nach rechts Assoziativität**|
|[Gleichheit](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Ungleichheit](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[\!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Gruppe 10 Rangfolge von links nach rechts Assoziativität**|
|[Bitweises AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Gruppe 11 Rangfolge von links nach rechts Assoziativität**|
|[Bitweises exklusives OR](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Gruppieren von 12 Rangfolge von links nach rechts Assoziativität**|
|[Bitweises inklusives OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Gruppe 13 Rangfolge von links nach rechts Assoziativität**|
|[Logisches AND](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Gruppe 14 Rangfolge von links nach rechts Assoziativität**|
|[Logisches OR](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Gruppieren von 15 Rangfolge, rechts-nach-links-Assoziativität**|
|[Bedingte](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Gruppieren von 16 Rangfolge, rechts-nach-links-Assoziativität**|
|[Zuweisung](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Multiplikationszuweisung](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Divisionszuweisung](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Modulozuweisung](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Additionszuweisung](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Subtraktionszuweisung](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Linksschiebezuweisung](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Rechtsschiebezuweisung](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Bitweise AND-Zuweisung](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Bitweise inklusive OR-Zuweisung](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Bitweise exklusive OR-Zuweisung](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Gruppieren von 17 Rangfolge, rechts-nach-links-Assoziativität**|
|[Throw-Ausdrucks](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Gruppieren von 18 Rangfolge von links nach rechts Assoziativität**|
|[Komma](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](operator-overloading.md)