---
title: Compilerfehler Fehler C2178 | Microsoft Docs
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: facb255b0c53a3de0e1d5c9f90de5835b25e3c32
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2178"></a>Compilerfehler Fehler C2178  
  
"*Bezeichner*"kann nicht mit deklariert werden"*Spezifizierer*' Spezifizierer  
  
Ein `mutable` Bezeichner wurde in einer Deklaration verwendet, aber der Bezeichner ist in diesem Kontext nicht zulässig.  
  
Die `mutable` -Bezeichner kann nur auf Namen von Klassenmembern-Daten angewendet werden und kann nicht angewendet werden, um deklarierten Namen `const` oder `static`, und kann nicht angewendet werden, um auf Elemente verweisen.  
  
## <a name="example"></a>Beispiel  
  
Im folgende Beispiel wird gezeigt, wie C2178 auftreten können und wie sie diesen Fehler beheben.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  

