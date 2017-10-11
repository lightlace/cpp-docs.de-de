---
title: Compilerfehler C2917 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2917
dev_langs:
- C++
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b66aee3abc57f7505f829fcedffdf2ffd927d839
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2917"></a>Compilerfehler C2917
'Name': Ungültiger Vorlagenparameter.  
  
 Eine Vorlagenparameterliste enthält einen Bezeichner, der kein Vorlagenparameter war.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2917 generiert:  
  
```  
// C2917.cpp  
// compile with: /c  
template<class T> class Vector {  
   void sort();  
};  
  
template<class T*> void Vector<T>::sort() {}   // C2917  
// try the following line instead  
// template<class T> void Vector<T>::sort() {}  
```
