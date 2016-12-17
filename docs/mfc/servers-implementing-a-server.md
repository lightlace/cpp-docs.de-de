---
title: "Server: Implementieren eines Servers"
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
  - "OLE-Serveranwendungen, Implementieren von OLE-Servern"
  - "Server, Implementieren"
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Server: Implementieren eines Servers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt den Code, den der MFC\-Anwendungs\-Assistent für eine visuelle Bearbeitung erstellt.  Wenn Sie nicht den Anwendungs\-Assistenten verwenden, führt dieses Artikels die Bereiche, in denen Sie Code schreiben müssen, um einer Serveranwendung zu implementieren.  
  
 Wenn Sie im Anwendungs\-Assistenten verwenden, um eine neue Anwendung erstellen, stellt sie eine signifikante Menge serverspezifischen Codes für Sie bereit.  Wenn Sie Visual Bearbeitungsserverfunktionalität in einer vorhandenen Anwendung hinzufügen, müssen Sie den Code dupliziert, den der Anwendungs\-Assistent vorausgesetzt hätte, bevor er den Rest des erforderlichen Servercode hinzufügen.  
  
 Der Servercode, dem der Anwendungs\-Assistent Fälle in mehrere Kategorien bereitstellt:  
  
-   Definieren von Serverressourcen:  
  
    -   Die Menüressource verwendet, wenn der Server ein eingebettetes Element in einem eigenen Fenster bearbeitet.  
  
    -   Die Menü\- und Symbolleistenressourcen verwendet, wenn der Server aktives gesorgt ist.  
  
     Weitere Informationen zu diesen Ressourcen, finden Sie unter [Menüs und Ressourcen: Server\-Hinzufügungen](../mfc/menus-and-resources-server-additions.md).  
  
-   Eine Elementklasse definieren wird von `COleServerItem` abgeleitet.  Weitere Details über Serverelemente, finden Sie unter [Server: Serverelemente](../mfc/servers-server-items.md).  
  
-   Ändern der Basisklasse der Dokumentklasse zu `COleServerDoc`.  Weitere Details finden Sie unter [Server: Implementieren von Server\-Dokumenten](../mfc/servers-implementing-server-documents.md).  
  
-   Eine Rahmenfensterklasse definieren wird von `COleIPFrameWnd` abgeleitet.  Weitere Details finden Sie unter [Server: Implementieren der direkten Rahmenfenstern](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Ein Eintrag für die Serveranwendung in der Windows\-Registrierungsdatenbank und \-c$registrieren der neuen Instanz des Servers mit dem OLE\-System erstellen.  Weitere Informationen zu diesem Thema, finden Sie unter [Registrierung](../mfc/registration.md).  
  
-   Die Serveranwendung initialisieren und startend.  Weitere Informationen zu diesem Thema, finden Sie unter [Registrierung](../mfc/registration.md).  
  
 Weitere Informationen finden Sie unter [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md) und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) in der Class Library Reference.  
  
## Siehe auch  
 [Server](../mfc/servers.md)   
 [Container](../mfc/containers.md)   
 [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Registrierung](../mfc/registration.md)