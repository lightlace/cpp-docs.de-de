---
title: "Compilerfehler C2732"
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
  - "C2732"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2732"
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2732
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bindungsangaben widersprechen vorheriger Angabe für 'function'  
  
 Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.  
  
 Dieser Fehler kann durch das Einbeziehen von Dateien mit unterschiedlichen Bindungsspezifizierern verursacht werden.  
  
 Um diesen Fehler zu beheben, ändern Sie die `extern`\-Anweisungen, sodass die Bindungen übereinstimmen.  Brechen Sie im Besonderen `#include`\-Direktive nicht in `extern "C"`\-Blöcke um.  
  
## Beispiel  
 Im folgenden Beispiel wird C2732 generiert:  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```