---
title: Compiler-Fehler C2798 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de30a19a2a27cde991cfce0ca061ce6f5447f033
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2798"></a>Compiler-Fehler C2798 generiert
'Super:: Member' ist mehrdeutig  
  
 Mehrere geerbte Strukturen enthalten, das Element, das Sie auf die verwiesen wird mit [super](../../cpp/super.md). Sie können entweder durch den Fehler beheben:  
  
-   Entfernen von B1 oder B2 aus der Vererbungsliste von D.  
  
-   Ändern des Namens des Datenmembers in B1 oder B2.  
  
 Im folgende Beispiel wird C2798 generiert:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```