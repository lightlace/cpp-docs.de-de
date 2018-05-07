---
title: Compilerfehler C3485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cd9de6f300fed673d588df60d7acca15b104b61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3485"></a>Compilerfehler C3485
Eine Lambdadefinition kann keine CV-Qualifizierer aufweisen.  
  
 Sie können keinen `const` - oder `volatile` -Qualifizierer als Teil der Definition eines Lambda-Ausdrucks verwenden.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `const` - oder `volatile` -Qualifizierer aus der Definition des Lambda-Ausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3485 erzeugt, weil der `const` -Qualifizierer als Teil der Definition eines Lambda-Ausdrucks verwendet wird:  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)