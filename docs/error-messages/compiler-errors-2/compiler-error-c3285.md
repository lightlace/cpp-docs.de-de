---
title: Compilerfehler C3285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3285
dev_langs:
- C++
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8991383147618d1168a9819ee02e2567cc4a6852
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3285"></a>Compilerfehler C3285
Die For Each-Anweisung kann nicht bei Variablen vom Typ "Typ" verwendet werden.  
  
 Mit der `for each` -Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt.  
  
 Weitere Informationen finden Sie unter [for each, in](../../dotnet/for-each-in.md) .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3285 generiert.  
  
```  
// C3285.cpp  
// compile with: /clr  
int main() {  
   for each (int i in 0) {}   // C3285   
  
   array<int> ^p = { 1, 2, 3 };  
   for each (int j in p) {}   // OK  
}  
```