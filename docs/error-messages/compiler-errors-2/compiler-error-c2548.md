---
title: Compilerfehler C2548 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2548
dev_langs:
- C++
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f05c036e7f7f5d78f2ca5a9acaa231ba3485d464
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2548"></a>Compilerfehler C2548
'class:: Member': Fehlender Standardparameter für Parameter angeben  
  
 Der Standardparameterliste fehlt ein Parameter. Wenn Sie einen Standardparameter an einer beliebigen Stelle in einer Parameterliste angeben, müssen Sie die Standardparameter für alle nachfolgenden Parameter definieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2548 generiert:  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```