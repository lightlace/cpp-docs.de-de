---
title: "Compilerfehler C2362"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2362"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2362"
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2362
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierung von 'Bezeichner' durch 'goto Marke' übersprungen  
  
 Wenn Sie mit [\/Za](../../build/reference/za-ze-disable-language-extensions.md) kompilieren und zu der Marke springen, wird die Initialisierung des Bezeichners verhindert.  
  
 Sprünge hinter eine Deklaration sind bei einer Initialisierung nicht zulässig, es sein denn, sie befindet sich innerhalb eines Blockes, der übergangen wird, oder die Variable wurde bereits initialisiert.  
  
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