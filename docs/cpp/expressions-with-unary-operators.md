---
title: "Ausdr&#252;cke mit un&#228;ren Operatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausdrücke [C++], Operatoren"
  - "Ausdrücke [C++], Unäre Operatoren"
  - "Unäre Operatoren, Ausdrücke mit"
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Ausdr&#252;cke mit un&#228;ren Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unäre Operatoren werden nur auf einen Operanden in einem Ausdruck angewendet.  Die unären Operatoren lauten wie folgt:  
  
-   [Dereferenzierungsoperator \(\*\)](../cpp/indirection-operator-star.md)  
  
-   [address\-of\-Operator \(&\)](../cpp/address-of-operator-amp.md)  
  
-   [Unärer Plus\-Operator \(\+\)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Unärer Negationsoperator \(–\)](../misc/unary-negation-operator.md)  
  
-   [Logischer Negationsoperator \(\!\)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [Einerkomplementierungsoperator \(~\)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [Präfixinkrement\-Operator \(\+\+\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Präfixdekrement\-Operator \(––\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Umwandlungsoperator \(\)](../cpp/cast-operator-parens.md)  
  
-   [sizeof\-Operator](../cpp/sizeof-operator.md)  
  
-   [\_\_uuidof\-Operator](../cpp/uuidof-operator.md)  
  
-   [\_\_alignof\-Operator](../cpp/alignof-operator.md)  
  
-   [new\-Operator](../cpp/new-operator-cpp.md)  
  
-   [delete\-Operator](../cpp/delete-operator-cpp.md)  
  
 Diese Operatoren weisen eine Assoziativität von rechts nach links auf.  Unäre Ausdrücke umfassen im Allgemeinen Syntax, die einem Postfix oder primären Ausdruck vorausgeht.  
  
 Folgende Formen von unären Ausdrücken sind möglich:  
  
-   *postfix\-expression*  
  
-   `++` *unary\-expression*  
  
-   `––` *unary\-expression*  
  
-   *unary\-operator* *cast\-expression*  
  
-   `sizeof` *unary\-expression*  
  
-   `sizeof(` *type\-name* `)`  
  
-   `decltype(` *expression* `)`  
  
-   *allocation\-expression*  
  
-   *deallocation\-expression*  
  
 Jede *postfix\-expression* gilt als *unary\-expression*, und da jeder primäre Ausdruck als *postfix\-expression* gilt, werden alle primären Ausdrücke ebenfalls als *unary\-expression* angesehen.  Weitere Informationen finden Sie unter [Postfixausdrücke](../cpp/postfix-expressions.md) und [Primäre Ausdrücke](../cpp/primary-expressions.md).  
  
 Ein *unary\-operator* besteht aus mindestens einem der folgenden Symbole: `* &` `+` `–` `!` `~`  
  
 Der *cast\-expression* ist ein unärer Ausdruck mit einer optionalen Umwandlung, um den Typ zu ändern.  Weitere Informationen finden Sie unter [Umwandlungsoperator: \(\)](../cpp/cast-operator-parens.md).  
  
 Ein *expression* kann ein beliebiger Ausdruck sein.  Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).  
  
 *allocation\-expression* bezieht sich auf den `new`\-Operator.  *deallocation\-expression* bezieht sich auf den `delete`\-Operator.  Weitere Informationen finden Sie unter den Links weiter oben in diesem Thema.  
  
## Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)