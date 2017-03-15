---
title: "Compilerfehler C2626 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2626"
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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