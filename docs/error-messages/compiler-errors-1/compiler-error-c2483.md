---
title: "Compilerfehler C2483 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2483"
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Objekte mit Konstruktoren oder Destruktoren können nicht als 'Thread' deklariert werden  
  
 Variablen, die mit dem `thread`\-Attribut deklariert wurden, können nicht mit einem Konstruktor oder einem anderen Ausdruck initialisiert werden, der eine Auswertung zur Laufzeit erfordert.  Es muss ein statischer Ausdruck verwendet werden, um `thread`\-Daten zu initialisieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C2483 generiert.  
  
```  
// C2483.cpp  
// compile with: /c  
__declspec(thread) struct A {  
   A(){}  
   ~A(){}  
} aa;   // C2483 error  
  
__declspec(thread) struct B {} b;   // OK  
```  
  
## Siehe auch  
 [Thread](../../cpp/thread.md)