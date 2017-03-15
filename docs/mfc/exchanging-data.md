---
title: "Datenaustausch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Eigenschaftenblätter"
  - "Austausch von Daten mit Eigenschaftenblättern"
  - "Eigenschaftenblätter, Datenaustausch"
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Datenaustausch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie bei den meisten Dialogfeldern, ist der Austausch von Daten zwischen dem Eigenschaftenblatt und der Anwendung eine der wichtigsten Features des Eigenschaftenblatts.  Dieser Artikel wird beschrieben, wie diese Aufgabe erfüllt.  
  
 Datenaustausch zwischen dem mit einem Eigenschaftenblatt handelt sich lediglich für den Austausch von Daten mit einzelnen Eigenschaftenseiten des Eigenschaftenblatts.  Die Prozedur für dem Austausch von Daten mit einer Eigenschaftenseite ist identisch mit der Aktivierungsreihenfolge für dem Austausch von Daten mit einem Dialogfeld, als [CPropertyPage](../mfc/reference/cpropertypage-class.md)\-Objekt gegenwärtig ein spezialisiertes [CDialog\-Klasse](../mfc/reference/cdialog-class.md)\-Objekt ist.  Die Prozedur genutzt die Funktion des Dialogdatenaustauschs des Frameworks \(DDX\), die dem Austausch von Daten zwischen Steuerelementen in einem Dialogfeld und Membervariablen des Dialogfelds ein.  
  
 Der wichtige Unterschied zwischen dem Austausch von Daten mit einem Eigenschaftenblatt und mit einem normalen Dialogfeld ist, dass das Eigenschaftenblatt mehrere Seiten verfügt, müssen Sie Daten mit allen Seiten im Eigenschaftenblatt.  Weitere Informationen über DDX, finden Sie unter [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md).  
  
 Das folgende Beispiel veranschaulicht dem Austausch von Daten zwischen einer Ansicht und zwei Seiten eines Eigenschaftenblatts:  
  
 [!CODE [NVC_MFCDocView#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#4)]  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)