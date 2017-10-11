---
title: Compilerfehler C3299 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3299
dev_langs:
- C++
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3612762f397914b6058516db7d8f56b840873c1e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3299"></a>Compilerfehler C3299
"Member_Funktion": Einschränkungen können nicht angegeben werden, sie werden von der Basismethode geerbt.  
  
 Wenn Sie eine generische Memberfunktion überschreiben, können Sie keine Einschränkungsklauseln angeben (das Wiederholen von Einschränkungen impliziert, dass die Einschränkungen nicht geerbt werden).  
  
 Die Einschränkungsklauseln für die generische Funktion, die Sie überschreiben, werden geerbt.  
  
 Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3299 generiert:  
  
```  
// C3299.cpp  
// compile with: /clr /c  
public ref struct R {  
   generic<class T>   
   where T : R  
   virtual void f();  
};  
  
public ref struct S : R {  
   generic<class T>   
   where T : R   // C3299  
   virtual void f() override;  
};  
```
