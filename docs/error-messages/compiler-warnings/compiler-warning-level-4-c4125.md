---
title: Compilerwarnung (Stufe 4) C4125 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4125
dev_langs:
- C++
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
caps.latest.revision: 6
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
ms.openlocfilehash: 1953f02549a8b57e6e2bb9dd4f206dfecb81f6e0
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4125"></a>Compilerwarnung (Stufe 4) C4125
Dezimale Ziffer beendet oktale Escapesequenz  
  
 Der Compiler wertet die oktale Zahl ohne die Dezimalziffer aus und geht davon aus, dass die Dezimalziffer ein Zeichen ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4125a.cpp  
// compile with: /W4  
char array1[] = "\709"; // C4125  
int main()  
{  
}  
```  
  
 Wenn die Ziffer 9 als Zeichen vorgesehen ist, korrigieren Sie das Beispiel wie folgt:  
  
```  
// C4125b.cpp  
// compile with: /W4  
char array[] = "\0709";  // C4125 String containing "89"  
int main()  
{  
}  
```
