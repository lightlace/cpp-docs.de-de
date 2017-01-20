---
title: "Verkn&#252;pfungstypen"
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
  - "Externe Verknüpfung, Verknüpfungstypen"
  - "Interne Verknüpfung, Verknüpfungstypen"
  - "Verknüpfung [C++], Keine"
  - "Verknüpfung [C++], Typen"
  - "Ohne Verknüpfung"
  - "Typen [C++], Verknüpfung"
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verkn&#252;pfungstypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Teilen von Namen von Objekten und Funktionen zwischen Übersetzungseinheiten wird als Verknüpfung bezeichnet.  Diese Namen können Folgendes aufweisen:  
  
-   Interne Verknüpfung, wobei sie sich nur auf Programmelemente innerhalb ihrer eigenen Übersetzungseinheiten beziehen. Sie werden nicht für andere Übersetzungseinheiten freigegeben.  
  
     Der gleiche Name in einer anderen Übersetzungseinheit bezieht sich möglicherweise auf ein anderes Objekt oder eine andere Klasse.  Namen mit interner Verknüpfung werden manchmal auch als lokal in ihren Übersetzungseinheiten bezeichnet.  
  
     Eine Beispieldeklaration eines Namens mit interner Verknüpfung ist:  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   Externe Verknüpfung, wobei sie sich auf Programmelemente in jeder Übersetzungseinheit im Programm beziehen können \- das Programmelement wird von den Übersetzungseinheiten gemeinsam genutzt.  
  
     Der gleiche Name in einer anderen Übersetzungseinheit bezieht sich auf das gleiche Objekt oder die gleiche Klasse.  Namen mit externer Verknüpfung werden manchmal auch als global bezeichnet.  
  
     Eine Beispieldeklaration eines Namens mit externer Verknüpfung ist:  
  
    ```  
    extern int i;  
    ```  
  
-   Keine Verknüpfung, wobei sie auf eindeutige Entitäten verweisen.  Der gleiche Name in einem anderen Bereich bezieht sich u. U. nicht auf dasselbe Objekt.  Ein Beispiel hierfür ist eine Enumeration.  \(Beachten Sie jedoch, dass Sie einen Zeiger auf ein Objekt ohne Verknüpfung übergeben können.  Dadurch wird das Objekt in anderen Übersetzungseinheiten verfügbar.\)  
  
## Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)