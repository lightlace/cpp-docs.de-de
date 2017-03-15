---
title: "Zugreifen auf den Dateistatus | Microsoft Docs"
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
  - "Beispiele [MFC], Dateistatus"
  - "Dateistatus [C++]"
  - "Dateien [C++], Aufrufen"
  - "Dateien [C++], Statusinformationen"
  - "Status der Dateien"
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Zugreifen auf den Dateistatus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CFile` unterstützt auch, die Dateistatus abruft, darunter, dass die Datei vorhanden, Erstellung und Das Änderungsdatum und \-zeiten, logische Größe und Pfad.  
  
### So erhalten Datei, \- von Dateien mithilfe des Standardarbeitsbereichs ab\)status  
  
1.  Verwenden Sie die [Die C\-Datei](../mfc/reference/cfile-class.md)\-Klasse, um Informationen zu einer Datei abzurufen und festzulegen.  Eine nützliche Anwendung, die `CFile` statische Memberfunktion **GetStatus** verwenden, um zu bestimmen, ob eine Datei vorhanden ist.  **GetStatus** gibt 0 zurück, wenn die angegebene Datei nicht vorhanden ist.  
  
 Daher können Sie das Ergebnis **GetStatus** verwenden, um festzustellen, ob **CFile::modeCreate** kennzeichnen verwendet, wenn eine Datei, z gezeigt durch das folgende Beispiel geöffnet ist:  
  
 [!CODE [NVC_MFCFiles#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCFiles#3)]  
  
 Weitere Informationen finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)