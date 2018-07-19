---
title: Compilerfehler C3865 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99a872d4cf7ed285a0798461c77adf904cfa3e71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275498"
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