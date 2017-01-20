---
title: "Compilerfehler C2071"
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
  - "C2071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2071"
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Ungültige Speicherklasse  
  
 `identifier` wurde mit einer ungültigen [Speicherklasse](../../c-language/c-storage-classes.md) deklariert.  Dieser Fehler kann verursacht werden, wenn mehr als eine Speicherklasse für einen Bezeichner angegeben ist oder wenn die Definition mit der Speicherklassen\-Deklaration nicht kompatibel ist.  
  
 Verstehen Sie zur Problembehebung die beabsichtigte Speicherklasse des Bezeichners – z. B. `static` oder `extern` und korrigieren Sie die Deklaration zur Übereinstimmung.  
  
## Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```