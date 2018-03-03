---
title: Compilerfehler C3865 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec5eabe6f4fa62648e9d3787d8ef2d2133f7736
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3865"></a>Compilerfehler C3865
'Aufrufkonvention': kann nur für systemeigene Memberfunktionen verwendet werden  
  
 Eine Aufrufkonvention wurde verwendet, auf eine Funktion, die entweder eine globale Funktion wurde oder in einer verwalteten Objektmemberfunktion. Die Aufrufkonvention kann nur auf eine Memberfunktion der systemeigenen (nicht verwalteten) verwendet werden.  
  
 Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
 Im folgende Beispiel wird C3865 generiert:  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```