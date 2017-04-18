---
title: Compilerfehler C3481 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
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
ms.openlocfilehash: 85157b7c90180eea034a87e3ae165710cefedf19
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3481"></a>Compilerfehler C3481
'var': Es wurde keine Lambdaerfassungsvariable gefunden.  
  
 Der Compiler konnte die Definition einer Variablen, die Sie an die Erfassungsliste eines Lambda-Ausdrucks übergeben haben, nicht finden.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Variable aus der Erfassungsliste des Lambdaausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3481 generiert, weil die `n` -Variable nicht definiert ist:  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
