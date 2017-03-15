---
title: "Compiler Error C2920 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2920"
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Error C2920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neudefinition: 'class': Klassenvorlage oder Generika wurde bereits als 'type' deklariert  
  
 Eine generische oder Vorlagenklasse weist mehrere Deklarationen auf, die nicht identisch sind.  Verwenden Sie zum Beheben dieses Fehlers unterschiedliche Name für unterschiedlichen Typen, oder entfernen Sie die Neudefinition des Typnamens.  
  
 Im folgenden Beispiel wird C2920 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 C2920 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
  
```