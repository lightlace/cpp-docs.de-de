---
title: Compilerfehler C3640 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3640
dev_langs:
- C++
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 493206e55be18d1e7cc00fec55dd2e111ad5026f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3640"></a>Compilerfehler C3640
'Member': eine referenzierte oder virtuelle Memberfunktion einer lokalen Klasse muss definiert werden  
  
 Der Compiler erfordert, dass bestimmte Funktionen definiert werden.  
  
 Im folgenden Beispiel wird C3640 generiert:  
  
```  
// C3640.cpp  
void f()   
{  
   struct S  
   {  
      virtual void f1();   // C3640  
      // Try the following line instead:  
      // virtual void f1(){}  
   };  
}  
```
