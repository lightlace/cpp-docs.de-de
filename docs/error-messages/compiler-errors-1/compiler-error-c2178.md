---
title: Compilerfehler Fehler C2178 | Microsoft Docs
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 96232cdb52fc84a90c768fa23b8a98da913c7982
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

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

