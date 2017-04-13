---
title: Compilerwarnung (Stufe 1) C4813 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4813
dev_langs:
- C++
helpviewer_keywords:
- C4813
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
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
ms.openlocfilehash: 30a288d4ed32d8908a41c8eeef5f5c2aca2b34c9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4813"></a>Compilerwarnung (Stufe 1) C4813
'Funktion': Eine Friend-Funktion einer lokalen Klasse muss bereits deklariert sein.  
  
 Eine Friend-Funktion in einer inneren Klasse wurde in der äußeren Klasse nicht deklariert.  
  
 Im folgenden Beispiel wird C4813 generiert:  
  
```  
// C4813.cpp  
// compile with: /W1 /LD  
void MyClass()  
{  
   // void func();  
   class InnerClass  
   {  
      friend void func();   // C4813 uncomment declaration above  
   };  
}  
```
