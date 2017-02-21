---
title: "Erstellen von Dokument/Ansicht | Microsoft Docs"
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
  - "Dokument-/Ansichtsarchitektur, Erstellen von Dokument/Ansicht"
  - "Dokumente, Erstellen"
  - "MFC, Dokumente"
  - "MFC, Ansichten"
  - "Objektersteller"
  - "Tabellen [C++]"
  - "Tabellen [C++], Objekte, die jedes MFC-Objekt erstellt"
  - "Ansichten, und Rahmenfenster"
  - "Ansichten, Erstellen"
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Erstellen von Dokument/Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Framework stellt die Implementierungen der `New` und **Öffnen** Befehle \(Ä\) im Menü **Datei**.  Erstellung eines neuen Dokuments und der zugeordneten Ansicht und Rahmenfensters ist ein kooperativer Aufwand unter Anwendungsobjekts, einer Normal\-Vorlage, dem neu erstellten Dokument und den neu erstellten Rahmenfenster.  Die folgende Tabelle fasst zusammen, der Objekte erstellen, was.  
  
### Objekt\-Ersteller  
  
|Creator|Erstellt|  
|-------------|--------------|  
|Application\-Objekt|Normal\-Vorlage|  
|Normal\-Vorlage|Document|  
|Normal\-Vorlage|Rahmenfenster|  
|Rahmenfenster|Ansicht|  
  
## Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Beziehungen zwischen MFC\-Objekten](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)