---
title: "Compilerfehler C3068 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3068"
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Eine naked\-Funktion kann keine Objekte enthalten, für die eine Entladung erforderlich wäre, wenn eine C\+\+\-Ausnahme auftritt  
  
 Der Compiler war nicht in der Lage, für eine [naked](../../cpp/naked-cpp.md)\-Funktion, die eine Ausnahme ausgelöst hat, eine Stapelentladung durchzuführen, da in der Funktion ein temporäres Objekt erstellt und die C\+\+\-Ausnahmebehandlung aktiviert wurde \([\/EHsc](../../build/reference/eh-exception-handling-model.md)\).  
  
 Um dieses Problem zu beheben, stellen Sie folgende Punkte sicher:  
  
-   Kompilieren Sie nicht mit \/EHsc.  
  
-   Kennzeichnen Sie die Funktion nicht als `naked`.  
  
-   Erstellen Sie kein temporäres Objekt in der Funktion.  
  
 Der Compiler bereinigt den Stapel beim Auftreten einer Ausnahme, wenn die folgenden Umstände vorliegen: Durch eine Funktion wird auf dem Stapel ein temporäres Objekt erstellt, durch die Funktion wird eine Ausnahme ausgelöst, und die C\+\+\-Ausnahmebehandlung ist aktiviert.  
  
 Wenn eine Ausnahme ausgelöst wird, wird compilergenerierter, Prolog und Epilog genannter Code für eine Funktion ausgeführt. Dieser Code ist in einer naked\-Funktion nicht vorhanden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3068 generiert:  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```