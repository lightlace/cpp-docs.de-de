---
title: Compiler-Fehler C2626 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2626
dev_langs:
- C++
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54cee1b985f53e25a0ceb2426231440f1a1bd9bb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2626"></a>Compiler-Fehler C2626 generiert
'identifier': Ein privates oder geschütztes Datenmember ist in einer anonymen Struktur oder Union nicht zulässig.  
  
 Ein Member einer anonymen Struktur oder Union muss über öffentlichen Zugriff verfügen.  
  
 Im folgenden Beispiel wird C2626 generiert:  
  
```  
// C2626.cpp  
int main() {  
   union {  
   protected:  
      int j;     // C2626, j is protected  
   private:  
      int k;     // C2626, k is private  
   };  
}  
```  
  
 Entfernen Sie zum Beheben dieses Problems private oder geschützte Tags:  
  
```  
// C2626b.cpp  
int main() {  
   union {  
   public:  
      int i;   // OK, i is public  
   };  
}  
```
