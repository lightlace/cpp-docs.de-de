---
title: Compilerfehler Fehler C2178 | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3727a66554b2e128061820df160c02a1370ebb74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171294"
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
