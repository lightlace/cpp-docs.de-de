---
title: Compilerfehler C2898 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2898
dev_langs:
- C++
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0833d3e4bab22673c6bca5aee64430134762e98f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2898"></a>Compilerfehler C2898
'Declaration': memberfunktionsvorlagen können nicht virtuell sein  
  
 Im folgende Beispiel wird C2898 generiert:  
  
```  
// C2898.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> virtual void f(T t) {}   // C2898  
};  
```
