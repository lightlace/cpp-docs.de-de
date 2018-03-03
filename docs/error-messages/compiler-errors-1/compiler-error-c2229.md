---
title: Compilerfehler C2229 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34add6428294d07a7dc1879bcbd10746a2a602d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2229"></a>Compilerfehler C2229
Typ "Identifier" wurde ein ungültiger NULL-array  
  
 Ein Member einer Struktur oder ein Bit enthält ein Array der Größe 0 (null), die nicht das letzte Element ist.  
  
 Da Sie als das letzte Element der Struktur der Array 0 (null) Größe aufweisen darf, müssen Sie seine Größe angeben, wenn Sie die Struktur zuordnen.  
  
 Wenn 0 (null) großen Arrays nicht das letzte Element der Struktur ist, kann der Compiler nicht den Offset für die verbleibenden Felder berechnen.  
  
 Im folgende Beispiel wird C2229 generiert:  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```