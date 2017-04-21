---
title: Inkrementierungs- und Dekrementierungsoperatoren | Microsoft-Dokumentation
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
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: 6
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
ms.openlocfilehash: b6922d841af51b2133ba3a5fb1b7f6bdbcc02a62
ms.lasthandoff: 04/01/2017

---
# <a name="prefix-increment-and-decrement-operators"></a>Inkrementierungs- und Dekrementierungsoperatoren in Präfixnotation
Die unären Operatoren (`++` und **--**) werden als „Präfix“-Inkrementoperator oder -Dekrementoperator bezeichnet, wenn die Inkrement- oder Dekrementoperatoren vor dem Operanden erscheinen. Das Postfixinkrementieren und -dekrementieren hat Vorrang vor Präfixinkrementieren und -dekrementieren. Der Operand muss Ganzzahltypen, Gleitkommatypen oder Zeigertypen aufweisen und muss ein veränderlicher L-Wertausdruck sein (ein Ausdruck ohne das **const**-Attribut). Das Ergebnis ist ein l-value.  
  
 Wenn der Operator vor dem Operanden angegeben wird, wird der Operand inkrementiert oder dekrementiert, und der neue Wert ist das Ergebnis des Ausdrucks.  
  
 Ein Operand vom Typ "Ganzzahl" oder "Gleitkomma" wird durch den ganzzahligen Wert 1 inkrementiert oder dekrementiert. Der Ergebnistyp entspricht dem Operandentyp. Ein Operand vom Zeigertyp wird um die Größe des von ihm adressierten Objekts inkrementiert oder dekrementiert. Ein inkrementierter Zeiger verweist auf das nächste Objekt. Ein dekrementierter Zeiger verweist auf das vorherige Objekt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht den unären Präfixdekrementoperator:  
  
```  
if( line[--i] != '\n' )  
    return;  
```  
  
 In diesem Beispiel wird die Variable `i` verringert, bevor sie als Index für `line` verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren (unär)](../c-language/c-unary-operators.md)
