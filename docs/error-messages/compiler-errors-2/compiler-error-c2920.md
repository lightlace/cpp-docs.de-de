---
title: "Compiler Error C2920"
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
  - "C2920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2920"
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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