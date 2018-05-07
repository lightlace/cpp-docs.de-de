---
title: Compiler-Fehler C2748 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2748
dev_langs:
- C++
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 336a2eb10f0a39f81547361e982aa744be88149e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2748"></a>Compiler-Fehler C2748 generiert
verwaltet oder WinRT-Arrayerstellung muss eine Arraygröße oder einen Arrayinitialisierung besitzen  
  
 Eine verwaltete oder ein WinRT-Array wurde nicht ordnungsgemäß formatiert. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C2748 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2748.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>();   // C2748  
   // try the following line instead  
   array<int> ^p2 = new array<int>(2);  
}  
```