---
title: "Compilerfehler C2601"
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
  - "C2601"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2601"
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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