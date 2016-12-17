---
title: "Bereinigen von Dokumenten und Ansichten"
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
helpviewer_keywords: 
  - "Dokumente, Bereinigung"
  - "Dokumente, Schließen"
  - "Ansichten, Bereinigung"
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Bereinigen von Dokumenten und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Dokument geschlossen werden, die Frameworkersten rufe die Memberfunktion [DeleteContents](../Topic/CDocument::DeleteContents.md).  Wenn Sie einen auf dem Heap Speicher während des Vorgangs des Dokuments ein, ist `DeleteContents` der optimale Ort, um es freizugeben.  
  
> [!NOTE]
>  Sie sollten Dokumentdaten im Destruktor des Dokuments nicht freigeben.  Bei einer SDI\-Anwendung würde das Dokumentobjekt möglicherweise wiederverwendet.  
  
 Sie können den Destruktor eine Ansicht überschreiben, um jedem Arbeitsspeicher freizugeben, den Sie auf dem Heap zugeordnet haben.  
  
## Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)