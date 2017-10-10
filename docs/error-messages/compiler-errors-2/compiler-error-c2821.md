---
title: Compilerfehler C2821 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f0218061b8d34eca00baa5834053d90711798bd0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2821"></a>Compilerfehler C2821
erster formaler Parameter auf "Operator new" muss 'unsigned Int' sein.  
  
Erster formaler Parameter von der [new-Operator](../../standard-library/new-operators.md#op_new) muss einen nicht signierten `int`.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2821 generiert:  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```
