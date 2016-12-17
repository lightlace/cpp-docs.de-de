---
title: "Aufrufbeispiel: Funktionsprototyp und Aufruf"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aufrufkonventionen, Beispiele [C++]"
  - "Beispiele [C++], Aufrufkonventionen"
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Aufrufbeispiel: Funktionsprototyp und Aufruf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Das folgende Beispiel zeigt die Ergebnisse eines Funktionsaufrufs mit unterschiedlichen Aufrufkonventionen.  
  
 Dieses Beispiel basiert auf dem folgenden Funktionsskelett.  Ersetzen Sie `calltype` durch die entsprechende Aufrufkonvention.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Weitere Informationen finden Sie im Abschnitt zu dem [Beispiel für die Ergebnisse eines Funktionsaufrufs](../cpp/results-of-calling-example.md).  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)