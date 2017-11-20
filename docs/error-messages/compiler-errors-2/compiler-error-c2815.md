---
title: Compilerfehler C2815 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2815
dev_langs:
- C++
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b6c438512dae910e0a42831e5f863f7b1766c097
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2815"></a>Compilerfehler C2815
"Operator delete": erster formaler Parameter muss ' "void" * ", aber es wurde 'Param' verwendet.  
  
 Eine benutzerdefinierte [Delete-Operator](../../standard-library/new-operators.md#op_delete) -Funktion muss einen ersten formalen Parameter vom Typ akzeptiert `void *`.  
  
 Im folgende Beispiel wird C2815 generiert:  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```