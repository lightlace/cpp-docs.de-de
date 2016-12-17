---
title: "Compilerwarnung (Stufe 1) C4722"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4722"
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„function“: Der Destruktor gibt nie Werte zurück, möglicherweise ist ein Speicherverlust aufgetreten.  
  
 Die Ablaufsteuerung wird mit einem Destruktor beendet. Der Thread oder das gesamte Programm wird beendet, und zugeordnete Ressourcen können möglicherweise nicht freigegeben werden.  Zudem ist das Verhalten der ausführbaren Datei nicht definiert, wenn ein Destruktor für die Stapelentladung während der Ausnahmeverarbeitung aufgerufen wird.  
  
 Zum Beheben dieses Fehlers entfernen Sie den Funktionsaufruf, der bewirkt, dass der Destruktor nicht zurückgegeben wird.  
  
## Beispiel  
 Im folgenden Beispiel wird C4722 generiert.  
  
```  
// C4722.cpp // compile with: /O1 /W1 /c #include <stdlib.h> class C { public: C(); ~C() { exit(1); };   // C4722 }; extern void func (C*); void Test(){ C x; func(&x); // control will not leave Test because destructor will exit }  
```