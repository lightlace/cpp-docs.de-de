---
title: Compilerfehler C3286 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80cda9575b604c9dd8e0000428c2d32a487079dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3286"></a>Compilerfehler C3286  
  
> "*Spezifizierer*': eine Iterationsvariable darf keine Speicherklassenspezifizierer aufweisen  
  
Eine Speicherklasse kann nicht auf eine Iterationsvariable angegeben werden. Weitere Informationen finden Sie unter [Speicherklassen (C++)](../../cpp/storage-classes-cpp.md) und [für jedes in](../../dotnet/for-each-in.md).  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Beispiel wird C3286 generiert und zeigt außerdem die richtige Verwendung.  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```