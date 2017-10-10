---
title: Compilerfehler C2897 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d3aa9ae6c79d3320104d9689f82b894cf2b76d9c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2897"></a>Compilerfehler C2897
ein Destruktor/Finalizer nicht mit einer Funktionsvorlage  
  
 Destruktoren oder Finalizer werden nicht überladen, ist die Deklaration eines Destruktors als Vorlage (die einen Satz von Destruktoren definiert würde) nicht zulässig.  
  
 Im folgende Beispiel wird C2897 generiert:  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2897 generiert.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2897 generiert.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```
