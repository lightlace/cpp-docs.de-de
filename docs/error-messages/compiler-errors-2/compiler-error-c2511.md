---
title: "Compilerfehler C2511"
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
  - "C2511"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2511"
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2511
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Überladene Memberfunktion nicht in "Klasse" gefunden  
  
 Keine Version der Funktion wurde mit den angegebenen Parametern deklariert.  Mögliche Ursachen:  
  
1.  An die Funktion wurden die falschen Parameter übergeben.  
  
2.  Die Parameter wurden in der falschen Reihenfolge übergeben.  
  
3.  Die Parameternamen wurden falsch geschrieben.  
  
 Im folgenden Beispiel wird C2511 generiert:  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```