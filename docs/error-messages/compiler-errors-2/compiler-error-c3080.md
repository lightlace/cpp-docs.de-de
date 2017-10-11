---
title: Compilerfehler C3080 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3080
dev_langs:
- C++
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fe5dd1e5c3609ed88c0083fa5d5b6cc7f4207567
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3080"></a>Compilerfehler C3080
'Finalizer_Funktion': Ein Finalizer kann keinen Speicherklassenspezifizierer aufweisen.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3080 generiert:  
  
```  
// C3080.cpp  
// compile with: /clr /c  
ref struct rs {  
protected:  
   static !rs(){}   // C3080  
   !rs(){}   // OK  
};  
```
