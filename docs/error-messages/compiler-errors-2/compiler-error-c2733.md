---
title: Compiler-Fehler C2733 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 22643ad7b1e801f2e4b9ee663c73f0d8fb97562d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2733"></a>Compiler-Fehler C2733 generiert
zweite C-Bindung für überladene Funktion 'Funktion' nicht zulässig  
  
 Mehr als einer überladenen Funktion mit C-Bindung deklariert wird. Wenn Sie C-Bindung verwenden, kann jeweils nur eine Art einer angegebenen Funktion externe sein. Da überladene Funktionen denselben nicht ergänzten Namen haben, können sie mit C-Programmen verwendet werden.  
  
 Im folgende Beispiel wird C2733 generiert:  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```
