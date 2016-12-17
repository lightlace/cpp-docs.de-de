---
title: "Compilerfehler C2657"
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
  - "C2657"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2657"
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2657
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::\*' zu Beginn einer Anweisung gefunden \(fehlt die Typangabe?\)  
  
 Die Zeile beginnt mit einem Bezeichner eines Memberzeigers.  
  
 Dieser Fehler kann durch einen fehlenden Typspezifizierer in der Deklaration eines Zeigers auf einen Member verursacht werden.  
  
 Im folgenden Beispiel wird C2657 generiert:  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```