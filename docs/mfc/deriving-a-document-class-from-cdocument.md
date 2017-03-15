---
title: "Ableiten einer Dokumentklasse von CDocument | Microsoft Docs"
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
  - "CDocument-Klasse, Ableiten von"
  - "Klassen [C++], Ableiten von CDocument"
  - "Abgeleitete Klassen, oft überschriebene Funktionen"
  - "Dokumentklassen, oft überschriebene Funktionen"
  - "Document-Objekte, Abgeleitet"
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Ableiten einer Dokumentklasse von CDocument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dokumente enthalten und verwalten die Daten der Anwendung.  Um die MFC\-Anwendung zu verwenden Assistent\-gab Dokumentklasse, muss Ihnen in folgenden Situationen an:  
  
-   Leiten Sie eine Klasse von **CDocument** für jeden Typ Dokument.  
  
-   Fügen Sie Membervariablen hinzu, um die Daten jedem Dokument zu speichern.  
  
-   Memberfunktion Überschreibungs **CDocument**`Serialize` in der Dokumentklasse.  `Serialize` schreibt und liest die Daten des Dokuments nach und vom Datenträger.  
  
## Andere dokumentieren die häufig überschriebenen Funktionen  
 Sie sollten auch anderen Memberfunktionen **CDocument** überschreiben.  Insbesondere müssen Sie häufig [OnNewDocument](../Topic/CDocument::OnNewDocument.md) und [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) überschreiben, um die Datenmember des Dokuments und [DeleteContents](../Topic/CDocument::DeleteContents.md) zu initialisieren, um dynamisch zugeordnete Daten zu zerstören.  Informationen über überschreibbare Member, Klasse finden Sie unter [CDocument](../mfc/reference/cdocument-class.md) in der *MFC\-Referenz*.  
  
## Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)