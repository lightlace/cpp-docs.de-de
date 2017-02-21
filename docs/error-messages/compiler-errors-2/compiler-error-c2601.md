---
title: "Compilerfehler C2601 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2601"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2601"
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2601
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Lokale Funktionsdefinitionen sind unzulässig  
  
 Der Code versucht, eine Funktion innerhalb einer Funktion zu definieren.  
  
 Im Quellcode kann unmittelbar vor der Stelle, an der Fehler C2601 auftritt, aber auch eine zusätzliche geschweifte Klammer stehen.  
  
 Im folgenden Beispiel wird C2601 generiert:  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```