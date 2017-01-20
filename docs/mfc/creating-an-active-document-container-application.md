---
title: "Erstellen einer Containeranwendung f&#252;r aktive Dokumente"
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
  - "Active Document-Container [C++], Erstellen"
  - "Aktive Dokumente [C++], Container"
  - "Anwendungen [MFC], Active Document-Container"
  - "Container [C++], aktives Dokument"
  - "MFC-COM [C++], Active Document-Einschluss"
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen einer Containeranwendung f&#252;r aktive Dokumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die einfachste und empfohlene Möglichkeit, eine Active Document\-Container\-Anwendung zu erstellen, besteht eine Containeranwendung MFC EXE\-Datei mit dem MFC\-Anwendungs\-Assistenten zu erstellen, ändert sich die Anwendung, Active Document\-Einschluss zu unterstützen.  
  
#### So eine Active Document\-Container\-Anwendung erstellen  
  
1.  Wählen Sie im Menü **Datei** klicken Sie auf  im Untermenü **Neu** auf **Projekt**.  
  
2.  Wählen Sie im linken Bereich klicken Sie auf **Visual C\+\+** Projekttyp.  
  
3.  Wählen Sie im rechten Bereich **MFC\-Anwendung** aus.  
  
4.  Nennen Sie das Projekt `MyProj`, klicken Sie auf **OK**.  
  
5.  Wählen Sie die Seite **Verbunddokumente** aus.  
  
6.  Wählen Sie **Container** oder die Option **Container\/Vollserver** aus.  
  
7.  Aktivieren Sie das Kontrollkästchen **Active Document\-Container**.  
  
8.  Klicken Sie auf **Fertig stellen**.  
  
9. Wenn der MFC\-Anwendungs\-Assistent beendet, die Anwendung zu generieren, öffnen Sie die folgenden Dateien im Projektmappen\-Explorer:  
  
    -   MyProjview.cpp  
  
10. In MyProjview.cpp nehmen Sie die folgenden Änderungen vor:  
  
    -   Ersetzen Sie in `CMyProjView::OnPreparePrinting` den Funktionsinhalt durch folgenden Code:  
  
         [!CODE [NVC_MFCDocView#56](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#56)]  
  
     `OnPreparePrinting` bietet Druckunterstützung.  Dieser Code ersetzt `DoPreparePrinting`, der die Standarddruckvorbereitung ist.  
  
     Active Document\-Einschluss stellt ein verbessertes Druckschema:  
  
    -   Sie können zuerst das aktive Dokument durch seine `IPrint`\-Schnittstelle und sie zu veranlassen, um sich zu drucken.  Dies ist zu vorherigen OLE\-Kapselung unterschiedlich, in der dem Container ein Bild des Elements auf das Drucker `CDC`\-Objekt rendern musste.  
  
    -   Wenn dies fehlschlägt, teilen Sie das enthaltende Element mit, um sich durch ihre `IOleCommandTarget`\-Schnittstelle zu drucken  
  
    -   Wenn dies fehlschlägt, können Sie Ihr eigenes Rendering vom Element.  
  
     Die statischen Memberfunktionen `COleDocObjectItem::OnPrint` und `COleDocObjectItem::OnPreparePrinting`, wie im vorherigen Code implementiert, behandeln dieses verbesserte Druckschema.  
  
11. Fügen Sie jeder Implementierung von eigenen hinzu und erstellen Sie die Anwendung.  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containment.md)