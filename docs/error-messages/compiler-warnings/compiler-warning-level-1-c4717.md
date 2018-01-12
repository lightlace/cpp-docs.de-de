---
title: Compilerwarnung (Stufe 1) C4717 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4717
dev_langs: C++
helpviewer_keywords: C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6f34baa3beb948f60247efcab9818e6fe6ed7f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4717"></a>Compilerwarnung (Stufe 1) C4717
'Funktion': rekursiv für alle Steuerelementpfade Funktion führt dazu, dass Laufzeit Stapelüberlauf  
  
 Jeder Pfad durch eine Funktion enthält einen Aufruf an die Funktion. Da es keine Möglichkeit gibt, die Funktion erst nach Aufrufen von sich selbst rekursiv beendet werden, wird die Funktion nie beendet.  
  
 Im folgenden Beispiel wird C4717 generiert:  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```