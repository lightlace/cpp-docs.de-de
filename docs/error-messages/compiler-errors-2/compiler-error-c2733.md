---
title: Compiler-Fehler C2733 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc1857cd800dd2d395754b9ae95094d9f57aad27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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