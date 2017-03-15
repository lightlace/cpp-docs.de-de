---
title: "Compilerfehler C2093 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2093"
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable1': Initialisierung mit der Adresse der automatischen Variablen 'Variable2' nicht möglich  
  
 Das Programm hat bei der Kompilierung mit [\/Za](../../build/reference/za-ze-disable-language-extensions.md) versucht, die Adresse einer automatischen Variablen als Initialisierer zu verwenden.  
  
 Im folgenden Beispiel wird C2093 generiert:  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```