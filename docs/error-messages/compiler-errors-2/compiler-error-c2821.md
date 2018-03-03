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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 842fa67c785173e658742e2b76a0957ded124515
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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