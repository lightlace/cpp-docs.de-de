---
title: Compilerfehler C2809 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2809
dev_langs:
- C++
helpviewer_keywords:
- C2809
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 07631cc909fb2423a737f44fd4fa07cea7d01d79
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2809"></a>Compilerfehler C2809
'Operator Operator' hat keine formalen Parameter  
  
 Der Operator fehlt ein erforderlicher Parameter.  
  
 Im folgende Beispiel wird C2809 generiert:  
  
```  
// C2809.cpp  
// compile with: /c  
class A{};  
int operator+ ();   // C2809  
int operator+ (A);   // OK  
```
