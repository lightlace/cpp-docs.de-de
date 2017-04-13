---
title: Compilerwarnung (Stufe 1) C4807 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
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
ms.openlocfilehash: 1548905fd242707c1cdf01c2cbc51b5c9e50cfce
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4807"></a>Compilerwarnung (Stufe 1) C4807
"Operation": Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"  
  
 Diese Warnung wird erzeugt, wenn ein vorzeichenbehaftetes Bitfeld der Länge 1 mit einer `bool` -Variablen verglichen wird. Da ein vorzeichenbehaftetes Bitfeld der Länge 1 nur die Werte -1 oder 0 enthalten kann, ist der Vergleich mit einem `bool`-Wert nicht unproblematisch. Keine Warnungen werden dagegen erzeugt, wenn `bool` -Werte mit vorzeichenlosen Bitfeldern der Länge 1 verglichen werden, da diese mit `bool` identisch sind und nur 0 oder 1 enthalten können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4807 generiert:  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```
