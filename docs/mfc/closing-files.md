---
title: "Schlie&#223;en von Dateien | Microsoft Docs"
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
  - "Dateien [C++], Schließen"
  - "MFC [C++], Dateivorgänge"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Schlie&#223;en von Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie sich in den E\/A\-Vorgänge, sobald Sie mit einer Datei beenden, müssen Sie sie schließen.  
  
#### So schließen eine Datei  
  
1.  Verwenden Sie die **Schließen**\-Memberfunktion.  Diese Funktion umfasst die Dateisystemdatei und die Leerenpuffer.  
  
 Wenn Sie den [Die C\-Datei](../mfc/reference/cfile-class.md)\-Objekt über den Frame \(wie im Beispiel gezeigt in [Öffnen von Dateien](../mfc/opening-files.md)\) zugeordnet, wird das Objekt automatisch geschlossen und anschließend zerstört, wenn es den Bereich verlässt.  Beachten Sie, dass das `CFile`\-Objekt gelöscht werden, wird nicht die eigentliche Datei im Dateisystem.  
  
## Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)