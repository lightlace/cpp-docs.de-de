---
title: Compiler-Fehler C2798 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4336577d3f2d1174dadb370db6001e982e9035f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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