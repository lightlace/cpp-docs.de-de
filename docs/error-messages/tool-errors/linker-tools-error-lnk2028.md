---
title: "Linkertoolfehler LNK2028"
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
  - "LNK2028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2028"
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verweis auf "exportierte\_Funktion" \(ergänzter\_Name\) in Funktion "Funktion\_mit\_Funktionsaufruf" \(ergänzter\_Name\)  
  
 Wenn eine systemeigene Funktion in ein reines Abbild importiert wird, unterscheiden sich die impliziten Aufrufkonventionen zwischen systemeigenen und reinen Kompilierungen.  
  
## Beispiel  
 In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen Funktion generiert, deren Aufrufkonvention implizit [\_\_cdecl](../../cpp/cdecl.md) ist.  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird ein reiner Client erstellt, der die systemeigene Funktion verwendet.  Die Aufrufkonvention unter **\/clr:pure** lautet jedoch [\_\_clrcall](../../cpp/clrcall.md).  Im folgenden Beispiel wird LNK2028 generiert.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```