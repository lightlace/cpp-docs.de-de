---
title: Compilerfehler C3286 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
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
ms.openlocfilehash: 551d5136cec63b968ce7b9711b06d8c7b509d9c8
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3286"></a>Compilerfehler C3286
"Spezifizierer": Eine Iterationsvariable darf keine Speicherklassenspezifizierer aufweisen.  
  
 Finden Sie unter [(NOTINBUILD) Speicherklassenspezifizierer](http://msdn.microsoft.com/en-us/10b3d22d-cb40-450b-994b-08cf9a211b6c) für Weitere Informationen.  
  
 Finden Sie unter [für jedes in](../../dotnet/for-each-in.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3286 generiert:  
  
```  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```
