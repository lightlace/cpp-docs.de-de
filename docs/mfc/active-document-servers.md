---
title: "Server f&#252;r aktive Dokumente | Microsoft Docs"
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
  - "aktive Dokumentserver [C++]"
  - "Aktive Dokumente [C++], Server"
  - "Server [C++], aktives Dokument"
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Server f&#252;r aktive Dokumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active Document\-Server wie Word, Excel \- oder PowerPoint\-Hostdokumente anderer Anwendungstypen können aktive Dokumente auf.  Im Gegensatz OLE \- gebettet Objekte \(die einfach in der anderen Seite eines Dokuments angezeigt werden\), stellen Active Documents die vollständige Schnittstelle und schließen systemeigene Funktionalität der Serveranwendung ab, die sie erstellt.  Benutzer Dokumente können mithilfe der Vollmacht ihrer Lieblings\-Anwendungen erstellen \(wenn das aktive Dokument aktiviert sind\), jedoch können das resultierende Projekt als einzelne Entität behandeln.  
  
 Active Documents können mehr als einer Seite verfügen und sind stets direkt aktiv.  Aktives DokumentSteuerteil der Benutzeroberfläche, die Menüs zusammenführend mit den **Datei** und **Hilfe** Menüs des Containers.  Sie werden die aggregierten Bearbeitungsbereich des Containers und steuern die Ansichten und Layout der Druckerseite \(Ränder, Fußzeilen, z.\).  
  
 MFC implementiert Active Document\-Server mit Dokument\/Ansichts\-Schnittstellen, Befehlsdispatchzuordnungen, Drucken, Menüverwaltung und Registrierungsverwaltung.  Bestimmte Programmierung Anforderungen werden in [Active Documents](../mfc/active-documents.md) erläutert.  
  
 MFC unterstützt aktive Dokumente mit der [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md), Klasse, die von [CCmdTarget](../mfc/reference/ccmdtarget-class.md) und [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md) abgeleitet ist, wird von [COleServerItem](../mfc/reference/coleserveritem-class.md) abgeleitet.  MFC unterstützt Active Document\-Container mit der [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md), Klasse, die von [COleClientItem](../mfc/reference/coleclientitem-class.md) abgeleitet ist.  
  
 `CDocObjectServer` ordnet den aktiven Dokumentoberflächen zu und initialisiert und ermöglicht ein aktives Dokument.  MFC stellt auch Makros zum Handlebefehlsrouting in den AKTIVEN Dokumente bereit.  Um aktive Dokumente in der Anwendung zu verwenden, schließen Sie AfxDocOb.h in der Datei StdAfx.h ein.  
  
 Ein regulärer MFC\-Server einbinden in seine eigene von `COleServerItem` abgeleitete Klasse.  Der MFC\-Anwendungs\-Assistent diese Klasse für Sie, wenn Sie das **Miniserver** oder **Vollserver** Kontrollkästchen, um die Anwendungsserververbunddokumentunterstützung zu geben.  Wenn Sie das Kontrollkästchen **Active Document\-Server** auswählen, generiert der MFC\-Anwendungs\-Assistent stattdessen eine Klasse, die von `CDocObjectServerItem` abgeleitet wird.  
  
 Die `COleDocObjectItem`\-Klasse ermöglicht einem OLE\-Container, um ein Active Document\-Container werden.  Sie können den MFC\-Anwendungs\-Assistenten verwenden, um einen Active Document\-Container erstellen, indem Sie das Kontrollkästchen **Active Document\-Container** in der Verbunddokument\-Supportseite des MFC\-Anwendungs\-Assistenten auswählen.  Weitere Informationen finden Sie unter [Erstellen einer Active Document\-Container\-Anwendung](../mfc/creating-an-active-document-container-application.md).  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containment.md)