---
title: Compilerfehler C2326 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2326
dev_langs:
- C++
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7365b0bfcb3bce1bf765a4dfcf0443524c5b6788
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2326"></a>Compilerfehler C2326
"Deklarator": Funktion kann nicht auf "Name" zugreifen  
  
 Der Code versucht, eine Membervariable zu ändern, was nicht möglich ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2326.cpp  
void MyFunc() {  
   int i;  
  
   class MyClass  {  
   public:  
      void mf() {  
         i = 4;   // C2326 i is inaccessible  
      }  
   };  
}  
```
