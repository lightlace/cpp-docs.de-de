---
title: Compilerfehler C2362 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e3a921084d696e6cf7abebc75d02d403cbcda2be
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2362"></a>Compilerfehler C2362
Initialisierung von 'Bezeichner' ist "Goto-Bezeichnung" übersprungen.  
  
 Beim Kompilieren mit ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md), Springen zur Bezeichnung verhindert, dass den Bezeichner initialisiert wird.  
  
 Sie können nicht hinter einer Deklaration mit einem Initialisierer springen, es sei denn, die Deklaration in einem Block eingeschlossen ist, die nicht eingegeben wird, oder die Variable wurde bereits initialisiert.  
  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```
