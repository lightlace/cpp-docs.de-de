---
title: Compilerfehler C2884 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5916eeb4195d163cd698a9398fa411f56ad8610
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2884"></a>Compilerfehler C2884
"Name": von using-Deklaration steht in Konflikt mit lokalen Funktion 'Funktion' eingeführt  
  
 Sie haben versucht, eine Funktion mehr als einmal zu definieren. Die erste Definition ist eine lokale Definition. Die zweite besteht aus einem Namespace mit einem `using` Deklaration.  
  
 Im folgende Beispiel wird C2884 generiert:  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```
