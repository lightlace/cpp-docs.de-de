---
title: "Initialisieren von Dokumenten und Ansichten | Microsoft Docs"
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
  - "Dokumente, Initialisieren"
  - "Initialisieren von Dokumenten"
  - "Initialisieren von Objekten, Document-Objekte"
  - "Initialisieren von Ansichten"
  - "Ansichten, Initialisieren"
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Initialisieren von Dokumenten und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dokumente werden auf zwei unterschiedliche Arten erstellt, daher muss die Dokumentklasse beide Methoden unterstützen.  Zum einen kann der Benutzer ein neues, leeres Dokument mit dem neuen Befehl der Datei erstellen.  In diesem Fall initialisiert Sie das Dokument in der Überschreibung der [OnNewDocument](../Topic/CDocument::OnNewDocument.md)\-Memberfunktion der Klasse [CDocument](../mfc/reference/cdocument-class.md).  Zweitens können den geöffneten Befehl im Menü Datei verwenden, ein neues Dokument zu erstellen, dessen Inhalt in einer Datei gelesen wird.  In diesem Fall initialisiert Sie das Dokument in der Überschreibung der [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md)\-Memberfunktion der Klasse **CDocument**.  Wenn beide Initialisierungen identisch sind, können Sie eine allgemeine Memberfunktion beider Überschreibungen aufrufen, oder `OnOpenDocument` kann `OnNewDocument` aufrufen, um ein reines Dokument initialisieren und den Öffnungsvorgang dann zu beenden.  
  
 Ansichten werden erstellt, nachdem ihre Dokumente erstellt sind.  Die beste Zeitpunkt, eine Ansicht zu initialisieren ist, nachdem das Framework beendet, das Dokument, das Rahmenfenster und die Ansicht zu erstellen.  Sie können die Ansicht initialisieren, indem Sie die Memberfunktion [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) von [CView](../mfc/reference/cview-class.md) überschreiben.  Wenn Sie initialisieren müssen, oder alle anpassen, sich jedes Mal, wenn das Dokument das ändert, können Sie [OnUpdate](../Topic/CView::OnUpdate.md) überschreiben.  
  
## Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)