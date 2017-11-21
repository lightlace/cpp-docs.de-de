---
title: Compilerfehler C3285 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3285
dev_langs: C++
helpviewer_keywords: C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a517ec1b163f3092b8dd161bee6cb348ab0129c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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