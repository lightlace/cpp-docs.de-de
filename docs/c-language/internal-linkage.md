---
title: "Interne Verkn&#252;pfung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Interne Verknüpfung"
  - "Verknüpfung [C++], interne"
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Interne Verkn&#252;pfung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die Deklaration eines Dateigültigkeitsbereichs\-Bezeichners für ein Objekt oder eine Funktion den *Speicherklassenspezifizierer* **static** enthält, hat der Bezeichner eine interne Bindung.  Andernfalls hat der Bezeichner eine externe Bindung.  Weitere Informationen erhalten Sie in der Erläuterung der *Speicherklassenspezifizierer*\-Nichtterminale unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 Innerhalb einer Übersetzungseinheit kennzeichnet jede Instanz eines Bezeichners mit interner Bindung denselben Bezeichner bzw. dieselbe Funktion.  Intern gebundene Bezeichner sind für eine Übersetzungseinheit eindeutig.  
  
## Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)