---
title: "lastprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "lastprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lastprivate OpenMP clause"
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# lastprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die einschließende Version des Kontexts der Variablen gleich der private Version von festgelegt wird, welcher Thread die letzte Iteration \(for\-Schleifen\-Konstrukt\) oder letzten Abschnitt ausführt \(\#pragma Abschnitten\).  
  
## Syntax  
  
```  
lastprivate(var)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var`  
 Die Variable, deren gleich private Version festgelegt wird, welcher Thread die letzte Iteration \(for\-Schleifen\-Konstrukt\) oder letzten Abschnitt ausführt \(\#pragma Abschnitten\).  
  
## Hinweise  
 `lastprivate` gilt für die folgenden Direktiven an:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [schedule](../../../parallel/openmp/reference/schedule.md) als ein Beispiel für die Verwendung von `lastprivate`\-Klausel.  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)