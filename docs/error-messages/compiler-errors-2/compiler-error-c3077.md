---
title: Compilerfehler C3077 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3077
dev_langs:
- C++
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9b966ac5941887369d8c15b7d9e2cf8f7e70f535
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3077"></a>Compilerfehler C3077
„finalizer“: Ein Finalizer kann nur ein Member eines Verweistyps sein.  
  
 Ein Finalizer kann nicht in einem systemeigenen oder Werttyp deklariert werden.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3077 generiert:  
  
```  
// C3077.cpp  
// compile with: /clr /c  
value struct vs {  
   !vs(){}   // C3077  
};  
  
ref struct rs {  
protected:  
   !rs(){}   // OK  
};  
```
