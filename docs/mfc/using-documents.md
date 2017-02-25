---
title: "Verwenden von Dokumenten | Microsoft Docs"
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
  - "Daten [MFC], Dokumente"
  - "Daten [MFC], Lesen"
  - "Dokument-/Ansichtsarchitektur [C++], Dokumente"
  - "Dokumente [C++]"
  - "Dokumente [C++], C++-Anwendungen"
  - "Dateien [C++]"
  - "Dateien [C++], Schreiben in"
  - "Drucken [MFC], Dokumente"
  - "Lesen von Daten [C++], Dokumente und Ansichten"
  - "Ansichten [C++], C++-Anwendungen"
  - "Schreiben in Dateien [C++]"
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Verwenden von Dokumenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zusammen arbeiten, Dokumente und Ansichten:  
  
-   Integrieren Sie, Verwalten und zeigen Sie das anwendungsspezifisches [Daten](../mfc/managing-data-with-document-data-variables.md).  
  
-   Erstellen einer Schnittstelle bestehendes [dokumentieren Sie Datenvariablen](../mfc/managing-data-with-document-data-variables.md) zum Bearbeiten der Daten.  
  
-   Angenommen [Schreiben und Lesen von Dateien](../mfc/serializing-data-to-and-from-files.md) beteiligt.  
  
-   Angenommen [Drucken](../mfc/role-of-the-view-in-printing.md) beteiligt.  
  
-   [Handle](../mfc/handling-commands-in-the-document.md) die Befehle und Meldungen der Anwendung.  
  
 Das Dokument wird insbesondere eingesetzt, wenn von Daten verwaltet.  Speichern Sie Ihre Daten normalerweise in den Dokumentklassenmembervariablen.  Die Ansicht verwendet diese Variablen, um Daten für die Anzeige und Update zuzugreifen.  Der Standard\-Serialisierungsmechanismus des Dokuments verwaltet Lesen und Schreiben der Daten nach und Dateien.  Dokumente können Befehle \(aber nicht Windows\-Meldungen als **WM\_COMMAND**\) auch bearbeiten.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Ableiten einer Dokumentklasse von CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Verwaltung von Daten mit Dokumentdatenvariablen](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Serialisieren von Daten an und von Dateien](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Behandlungsbefehle im Dokument](../mfc/handling-commands-in-the-document.md)  
  
-   [Die OnNewDocument\-Memberfunktion](../Topic/CDocument::OnNewDocument.md)  
  
-   [Die DeleteContents\-Memberfunktion](../Topic/CDocument::DeleteContents.md)  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)