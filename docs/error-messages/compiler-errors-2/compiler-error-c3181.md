---
title: Compiler-Fehler C3181 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 84f725f64e22dc5da1736eb64696b03b0b7ea36a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3181"></a>Compiler-Fehler C3181 generiert
'Typ': Ungültiger Operand für Operator  
  
Ein ungültiger Parameter wurde übergeben, um die [Typeid](../../windows/typeid-cpp-component-extensions.md) Operator. Der Parameter muss ein verwalteter Typ sein.  
  
Beachten Sie, dass der Compiler Aliase für systemeigene Typen verwendet, die in der common Language Runtime-Typen zugeordnet.  
  
Im folgende Beispiel wird C3181 generiert:  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  

