---
title: Compilerfehler C3531 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7753e30e305b7b36adc3b4d2b535f755fa455bdd
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3531"></a>Compilerfehler C3531
'Symbol': ein Symbol, dessen Typ 'auto' enthält, muss einen Initialisierer haben  
  
 Einen Initialisierungsausdruck keinen für die angegebene Variable.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie einen Initialisierungsausdruck, z. B. eine einfache Zuweisung, die Gleichheitszeichensyntax, verwendet werden, wenn die Variable zu deklarieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel C3531, da Variablen `x1`, `y1, y2, y3`, und `z2` nicht initialisiert werden.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)
