---
title: "Compilerwarnung (Stufe 3) C4390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4390"
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 3) C4390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

";": Leere kontrollierte Anweisung aufgetreten; ist dies beabsichtigt?  
  
 Ein Semikolon wurde hinter einer Steueranweisung gefunden, die keine Anweisungen enthält.  
  
 Wenn C4390 aufgrund eines Makros ausgegeben wird, sollten Sie das Pragma [warning](../../preprocessor/warning.md) verwenden, um C4390 in dem Modul zu deaktivieren, in dem das Makro enthalten ist.  
  
 Im folgenden Beispiel wird C4390 generiert:  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```