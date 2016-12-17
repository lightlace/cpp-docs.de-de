---
title: "Keine Verkn&#252;pfung"
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
  - "Verknüpfung [C++], Keine"
  - "Ohne Verknüpfung"
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Keine Verkn&#252;pfung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Deklaration für einen Bezeichner in einem Block den `extern`\-Speicherklassenspezifizierer nicht enthält, hat der Bezeichner keine Bindung und ist für die Funktion eindeutig.  
  
 Die folgenden Bezeichner haben keine Verknüpfung:  
  
-   Ein Bezeichner, der als etwas anderes als ein Objekt oder eine Funktion deklariert wurde  
  
-   Ein Bezeichner, der zum Funktionsparameter deklariert wurde  
  
-   Ein Blockbereichsbezeichner für ein Objekt, das ohne den `extern`\-Speicherklassenspezifizierer deklariert wurde  
  
 Wenn ein Bezeichner keine Verknüpfung aufweist, wird durch erneutes Deklarieren des gleichen Namens \(in einem Deklarator oder Typspezifizierer\) auf der gleichen Gültigkeitsebene einen Fehler bei der Symbolneudefinition.  
  
## Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)