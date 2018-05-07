---
title: Compilerfehler C3531 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69fcacacafba752f77aacd55d5cd57b2c42b5ba9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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