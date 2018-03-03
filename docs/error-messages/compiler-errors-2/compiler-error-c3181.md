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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b083084fab3970d3eecfe846917585bd8ef51df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
