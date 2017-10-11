---
title: Compilerfehler C3638 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 51048bb46dde49f432699e620b94d62fb8f6c131
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3638"></a>Compilerfehler C3638
'Operator': das standard-Boxing und unboxing Konvertierungsoperatoren können nicht neu definiert werden  
  
 Der Compiler definiert einen Konvertierungsoperator für jede verwaltete Klasse implizites Boxing unterstützt. Dieser Operator kann nicht neu definiert werden.  
  
 Weitere Informationen finden Sie unter [implizites Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3638 generiert:  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```
