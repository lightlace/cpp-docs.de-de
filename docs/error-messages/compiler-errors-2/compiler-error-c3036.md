---
title: Compilerfehler C3036 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3036
dev_langs:
- C++
helpviewer_keywords:
- C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7682dc0aa8421c7febbc2c8eafe576867ed70ed3
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3036"></a>Compilerfehler C3036
"Operator": Ungültiges Operatortoken in der "reduction"-Klausel von OpenMP.  
  
 Eine [reduction](../../parallel/openmp/reference/reduction.md) -Klausel wurde nicht ordnungsgemäß angegeben.  
  
 Im folgenden Beispiel wird C3036 generiert:  
  
```  
// C3036.cpp  
// compile with: /openmp  
static float a[1000], b[1000], c[1000];  
void test1(int first, int last) {  
   static float dp = 0.0f;  
   #pragma omp for nowait reduction(.:dp)   // C3036  
   // try the following line instead  
   // #pragma omp for nowait reduction(+: dp)  
   for (int i = first ; i <= last ; ++i)  
      dp += a[i] * b[i];  
}  
```
