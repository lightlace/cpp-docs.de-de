---
title: Compilerfehler C3888 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4b85385c97f5873c1b370cd72f0866439263f787
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3888"></a>Compilerfehler C3888
"name": Der diesem literal-Datenmember zugeordnete Konstantenausdruck wird von C++/CLI nicht unterstützt  
  
 Die *Namen* Datenmember, die mit deklariert wird die [literal](../../windows/literal-cpp-component-extensions.md) Schlüsselwort wird initialisiert, mit einem Wert, der vom Compiler nicht unterstützt. Der Compiler unterstützt nur konstante integrale, Enumerations- oder Zeichenfolgentypen. Der Fehler **C3888** wurde wahrscheinlich dadurch verursacht, dass das Datenmember mit einem Bytearray initialisiert wird.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass das deklarierte literal-Datenmember ein unterstützter Typ ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenliterale](../../windows/literal-cpp-component-extensions.md)
