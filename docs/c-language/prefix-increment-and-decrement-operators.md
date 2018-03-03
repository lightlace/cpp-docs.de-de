---
title: Inkrementierungs- und Dekrementierungsoperatoren | Microsoft-Dokumentation
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
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84d8c3f5a1b43fdec5554003e32db4f23b4f0406
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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