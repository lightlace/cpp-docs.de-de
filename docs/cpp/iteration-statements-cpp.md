---
title: "Iterationsanweisungen (C++)"
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
  - "Iterationsanweisungen"
  - "Schleifenstruktur, Iterationsanweisungen"
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Iterationsanweisungen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Iterationsanweisungen bewirken, dass Anweisungen \(oder Verbundanweisungen\) NULL mal oder mehrmals ausgeführt werden, je nach LOOP\-Beendigungskriterien.  Wenn diese Anweisungen Verbundanweisungen sind, werden sie nacheinander ausgeführt, es sei denn, die [break](../cpp/break-statement-cpp.md)\-Anweisung oder die [continue](../cpp/continue-statement-cpp.md)\-Anweisung wird gefunden.  
  
 C\+\+ stellt vier Iterationsanweisungen bereit – [while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) und [range\-based for](../cpp/range-based-for-statement-cpp.md).  Jedes dieser Elemente wird durchlaufen, bis der Beendigungsausdruck mit null \(false\) ausgewertet oder die Beendigung der Schleife mit einer **break**\-Anweisung erzwungen wird.  In der folgenden Tabelle werden diese Anweisungen und ihre Aktionen zusammengefasst. Jede von ihnen wird in den folgenden Abschnitten im Detail behandelt.  
  
### Iterationsanweisungen  
  
|Anweisung|Ausgewertet an|Initialisierung|Inkrement|  
|---------------|--------------------|---------------------|---------------|  
|`while`|Anfang der Schleife|Nein|Nein|  
|**do**|Ende der Schleife|Nein|Nein|  
|**for**|Anfang der Schleife|Ja|Ja|  
|**range\-based for**|Anfang der Schleife|Ja|Ja|  
  
 Der Anweisungsteil einer Iterationsanweisung kann keine Deklaration sein.  Es kann jedoch eine Verbundanweisung sein, die eine Deklaration enthält.  
  
## Siehe auch  
 [Übersicht über C\+\+\-Anweisungen](../cpp/overview-of-cpp-statements.md)