---
title: "Schlie&#223;en von Dateien"
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
  - "Dateien [C++], Schließen"
  - "MFC [C++], Dateivorgänge"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Schlie&#223;en von Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie sich in den E\/A\-Vorgänge, sobald Sie mit einer Datei beenden, müssen Sie sie schließen.  
  
#### So schließen eine Datei  
  
1.  Verwenden Sie die **Schließen**\-Memberfunktion.  Diese Funktion umfasst die Dateisystemdatei und die Leerenpuffer.  
  
 Wenn Sie den [Die C\-Datei](../mfc/reference/cfile-class.md)\-Objekt über den Frame \(wie im Beispiel gezeigt in [Öffnen von Dateien](../mfc/opening-files.md)\) zugeordnet, wird das Objekt automatisch geschlossen und anschließend zerstört, wenn es den Bereich verlässt.  Beachten Sie, dass das `CFile`\-Objekt gelöscht werden, wird nicht die eigentliche Datei im Dateisystem.  
  
## Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)