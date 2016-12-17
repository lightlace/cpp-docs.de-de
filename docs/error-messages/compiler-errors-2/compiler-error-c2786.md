---
title: "Compilerfehler C2786"
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
  - "C2786"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2786"
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2786
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ungültiger Operand für \_\_uuidof  
  
 Der Operator [\_\_uuidof](../../cpp/uuidof-operator.md) akzeptiert entweder einen mit einer GUID verbundenen benutzerdefinierten Typ oder ein Objekt eines solchen benutzerdefinierten Typs.  Mögliche Ursachen:  
  
1.  Das Argument ist kein benutzerdefinierter Typ.  
  
2.  `__uuidof` kann die GUID nicht aus dem Argument extrahieren.  
  
 Im folgenden Beispiel wird C2786 generiert:  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```