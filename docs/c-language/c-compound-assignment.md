---
title: C-Verbundzuweisung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
caps.latest.revision: 7
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 85fb149dcfb104a9b2e094deef83c3b33d1b7b6c
ms.lasthandoff: 04/01/2017

---
# <a name="c-compound-assignment"></a>C-Verbundzuweisung
Die Verbundzuweisungsoperatoren kombinieren den Einfachzuweisungsoperator mit einem anderen binären Operator. Verbundzuweisungsoperatoren führen einen Vorgang aus, der vom zusätzlichen Operator angegeben wurde, und weisen das Ergebnis dann dem linken Operanden zu. Zum Beispiel kann ein Verbundzuweisungsausdruck wie  
  
```  
  
expression1  
+=  
expression2  
  
```  
  
 verstanden werden als  
  
```  
  
expression1  
=  
expression1  
+  
expression2  
  
```  
  
 Allerdings ist der Verbundzuweisungsausdruck nicht mit der erweiterten Version äquivalent, da der Verbundzuweisungsausdruck *expression1* nur einmal auswertet, während die erweiterte Version *expression1* zweimal auswertet: in der Additions- und in der Zuweisungsoperation.  
  
 Die Operanden des Verbundzuweisungsoperators müssen vom Typ „Ganzzahl“ oder „Gleitkomma“ sein. Jeder Verbundzuweisungsoperator führt die Konvertierungen aus, die der entsprechende binäre Operator ausführt, und schränkt die Typen seiner Operanden entsprechend ein. Die Operatoren für die Additionszuweisung (`+=`) und die Subtraktionszuweisung (**-=**) können über einen linken Operanden vom Zeigertyp verfügen. In diesem Fall muss der rechte Operand integralen Typs sein. Das Ergebnis eines Verbundzuweisungsvorgangs hat den Wert und Typ des linken Operanden.  
  
```  
#define MASK 0xff00  
  
n &= MASK;  
```  
  
 In diesem Beispiel wird ein bitweiser inklusiver AND-Vorgang für `n` und `MASK` ausgeführt, und das Ergebnis wird `n` zugewiesen. Die Manifestkonstante `MASK` wird mit einer [#define](../preprocessor/hash-define-directive-c-cpp.md)-Präprozessoranweisung definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)
