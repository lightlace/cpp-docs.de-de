---
title: Compilerfehler C2874 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5567e796dca8161491e0764523140b516bce886
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2874"></a>Compilerfehler C2874
using-Deklaration verursacht eine mehrfache Deklaration von 'Symbol'  
  
 Die Deklaration bewirkt, dass das gleiche Element zweimal definiert werden.  
  
 Im folgende Beispiel wird C2874 generiert:  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```
