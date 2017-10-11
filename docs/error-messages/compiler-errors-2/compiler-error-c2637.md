---
title: Compiler-Fehler C2637 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2637
dev_langs:
- C++
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f676205e2850e411ddb5e5b996114c00c65087f2
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2637"></a>Compiler-Fehler C2637 generiert
'Bezeichner': Zeiger auf Datenmember kann nicht geändert werden.  
  
 Ein Zeiger auf einen Datenmember kann nicht durch eine Aufrufkonvention haben. Um zu beheben, entfernen Sie die Aufrufkonvention oder deklarieren Sie einen Zeiger auf eine Memberfunktion zu.  
  
 Im folgende Beispiel wird C2637 generiert:  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```
