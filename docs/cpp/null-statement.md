---
title: "NULL-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausdrücke [C++], NULL"
  - "NULL-Anweisung"
  - "NULL-Werte, Ausdrücke"
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# NULL-Anweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die "NULL\-Anweisung" ist eine Ausdrucksanweisung, bei der die *Anweisung* fehlt.  Dies ist nützlich, wenn in der Syntax der Sprache eine Anweisung erwartet wird, jedoch keine Ausdrucksauswertung.  Die Anweisung besteht aus einem Semikolon.  
  
 NULL\-Anweisungen werden normalerweise als Platzhalter in Iterationsanweisungen oder als Anweisungen verwendet, um Bezeichnungen am Ende von Verbundanweisungen oder Funktionen zu platzieren.  
  
 Das folgende Codefragment zeigt, wie Sie eine Zeichenfolge zu einer anderen kopieren und die NULL\-Anweisung integrieren:  
  
```  
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## Siehe auch  
 [Ausdrucksanweisung](../cpp/expression-statement.md)