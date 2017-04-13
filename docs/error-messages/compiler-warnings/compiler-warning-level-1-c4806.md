---
title: Compilerwarnung (Stufe 1) C4806 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
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
ms.openlocfilehash: 021b0a5fd91df53e8fd1cb297c5d697f7135ff89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4806"></a>Compilerwarnung (Stufe 1) C4806
"operation": unsichere Operation: kein Wert vom Typ "type" erweitert auf Typ "type" kann mit der angegebenen Konstante übereinstimmen  
  
 Diese Meldung warnt Sie vor Code wie `b == 3`, wobei `b` Typ `bool`aufweist. Aufgrund der Erweiterungsregeln wird `bool` auf `int`erweitert. Dies ist zulässig, es kann aber nie **true**sein. Im folgenden Beispiel wird C4806 generiert:  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```
