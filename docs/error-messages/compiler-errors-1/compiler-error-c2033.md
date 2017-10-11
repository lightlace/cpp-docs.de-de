---
title: Compilerfehler C2033 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2033
dev_langs:
- C++
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ba0fcc5d0938c796c94e6201be18d6c1fb6158b0
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2033"></a>Compilerfehler C2033
'Bezeichner': Bitfelder dürfen keine Dereferenzierungen haben.  
  
 Das Bitfeld wurde als Zeiger deklariert, was nicht zulässig ist.  
  
 Im folgenden Beispiel wird C2033 generiert:  
  
```  
// C2033.cpp  
struct S {  
   int *b : 1;  // C2033  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2033b.cpp  
// compile with: /c  
struct S {  
   int b : 1;  
};  
```
