---
title: Compilerfehler C2184 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2184
dev_langs:
- C++
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
caps.latest.revision: 9
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
ms.openlocfilehash: ce828742e8b05435f5135b1d58ce17ad3f8c5f2b
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2184"></a>Compilerfehler C2184
"Typ": Ungültiger Typ für __except-Ausdruck, muss eine ganze Zahl sein.  
  
 Ein Typ wurde verwendet ein [__except](../../c-language/try-except-statement-c.md) -Anweisung, aber der Typ ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2184 generiert:  
  
```  
// C2184.cpp  
void f() {  
   int * p;  
   __try{}  
   __except(p){};   // C2184  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2184b.cpp  
// compile with: /c  
void f() {  
   int i = 0;  
   __try{}  
   __except(i){};  
}  
```
