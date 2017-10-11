---
title: Compilerfehler C3914 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3914
dev_langs:
- C++
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4d38483d3edd477babb7a240a7b79841850f6a9e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3914"></a>Compilerfehler C3914
eine Standardeigenschaft kann nicht statisch sein.  
  
Eine Standardeigenschaft wurde falsch deklariert.  Weitere Informationen finden Sie unter [wie: Verwenden von Eigenschaften in C + c++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C3914 generiert und gezeigt, wie sie diesen Fehler beheben.  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```
