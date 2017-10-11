---
title: Compilerfehler C3470 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3470
dev_langs:
- C++
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7ae5a2d2d95c3ab6a521493874b416c87d4e5a9b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3470"></a>Compilerfehler C3470
"Typ": Eine Klasse kann nicht gleichzeitig einen Indexer (indizierte Standardeigenschaft) und einen []-Operator aufweisen.  
  
 Ein Typ kann nicht sowohl einen Standardindexer als auch einen []-Operator definieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3470 generiert:  
  
```  
// C3470.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R {  
public:  
   property int default[int] {  
      int get(int i) {  
         return i+1;  
      }  
   }  
  
   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470  
};  
  
int main() {  
   R ^ r = gcnew R;  
   // return r[9] + r["32"] - 42;  
}  
```
