---
title: Compilerfehler C3895 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3895
dev_langs:
- C++
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75bd27d44ed74817cc23e6b58f036742d2d1979b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3895"></a>Compilerfehler C3895
'Var': Typ-Datenmember können nicht 'volatile' sein  
  
 Bestimmte Arten von Datenelementen, z. B. [literal](../../windows/literal-cpp-component-extensions.md) oder [Initonly](../../dotnet/initonly-cpp-cli.md), nicht mit [volatile](../../cpp/volatile-cpp.md).  
  
 Im folgende Beispiel wird C3895 generiert:  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```