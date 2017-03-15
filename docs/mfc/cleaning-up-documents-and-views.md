---
title: "Bereinigen von Dokumenten und Ansichten | Microsoft Docs"
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
  - "Dokumente, Bereinigung"
  - "Dokumente, Schließen"
  - "Ansichten, Bereinigung"
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Bereinigen von Dokumenten und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Dokument geschlossen werden, die Frameworkersten rufe die Memberfunktion [DeleteContents](../Topic/CDocument::DeleteContents.md).  Wenn Sie einen auf dem Heap Speicher während des Vorgangs des Dokuments ein, ist `DeleteContents` der optimale Ort, um es freizugeben.  
  
> [!NOTE]
>  Sie sollten Dokumentdaten im Destruktor des Dokuments nicht freigeben.  Bei einer SDI\-Anwendung würde das Dokumentobjekt möglicherweise wiederverwendet.  
  
 Sie können den Destruktor eine Ansicht überschreiben, um jedem Arbeitsspeicher freizugeben, den Sie auf dem Heap zugeordnet haben.  
  
## Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)