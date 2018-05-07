---
title: Compilerfehler C2874 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aebe8054c68e1474a2597da5bda7bb985eb205dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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