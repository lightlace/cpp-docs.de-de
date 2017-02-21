---
title: "OLE-Hintergrund: Implementierungsstrategien | Microsoft Docs"
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
  - "Anwendungen [OLE], OLE implementieren"
  - "OLE [C++], Entwicklungsstrategie"
  - "OLE-Anwendungen [C++], OLE implementieren"
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OLE-Hintergrund: Implementierungsstrategien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Je nach Anwendung gibt es vier beliebige Durchführungsstrategien für das Hinzufügen von OLE\-Unterstützung:  
  
-   Sie schreiben eine neue Anwendung.  
  
     Diese Situation erfordert normalerweise die wenigsten Arbeit.  Sie führen den MFC\-Anwendungs\-Assistenten und wählen entweder erweiterte Features oder Verbunddokument\-Unterstützung aus, um ein Anwendungsskelett zu erstellen.  Informationen über diese Optionen und ihre Aufgaben, finden Sie im Artikel [Erstellen eines Programms mit MFC](../mfc/reference/mfc-application-wizard.md).  
  
-   Sie haben ein Programm, das mit der Microsoft Foundation Class\-Bibliotheks\-Version 2.0 oder höher, die OLE, geschrieben wird nicht unterstützt.  
  
     Erstellen Sie eine neue Anwendung mit dem MFC\-Anwendungs\-Assistenten wie bereits erwähnt und kopieren und einfügen der Code von der neuen Anwendung in die vorhandene Anwendung.  Dies funktioniert für Server, Container oder automatisierte Anwendungen.  Siehe das Beispiel MFC\- [SCRIBBLE](../top/visual-cpp-samples.md) als Beispiel dieser Strategie.  
  
-   Sie haben ein Microsoft Foundation Class\-Bibliotheks\-Programm, das Unterstützung OLE\-Version 1.0 implementiert.  
  
     [MFC\-technischer Hinweis 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) finden Sie diese Konvertierungsstrategie.  
  
-   Sie haben eine Anwendung, die geschrieben wurden nicht mit Microsoft Foundation Classes, möglicherweise implementiert und die OLE\-Unterstützung.  
  
     Diese Situation erfordert die meiste Arbeit.  Ein Ansatz ist, eine neue Anwendung, wie in der ersten Strategie und kopieren und einfügen der vorhandene Code in die Datei zu erstellen.  Wenn der vorhandene Code in C geschrieben wird, müssen Sie sie ändern, sodass er als C\+\+\-Code kompilieren.  Wenn das C\-Code Windows\-API aufruft, müssen Sie sie ändern, um die Microsoft Foundations\-Klassen zu verwenden.  Dieser Ansatz wahrscheinlich benötigt eine Restrukturierung des Programms, die Dokument\-\/Ansichtarchitektur zu unterstützen, die von den Versionen 2.0 und höher \(Microsoft Foundation Classes verwendet wird.  Weitere Informationen über diese Architektur, finden Sie unter [Technischer Hinweis 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Nachdem Sie auf eine Strategie festlegen, sollten Sie entweder die [Container](../mfc/containers.md) oder [Server](../mfc/servers.md) lesen Artikel \(abhängig vom Typ der Anwendung, die Sie schreiben\) oder der Beispielprogramme überprüfen oder beides.  Die Beispiele [OCLIENT](../top/visual-cpp-samples.md) und [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE zeigen, wie die verschiedenen Aspekte von Containern und Servern bzw., implementiert.  An verschiedenen Zeitpunkten während dieser Artikel, sind Sie angesprochene bestimmte Funktionen in diesen Beispielen als Beispiele der Verfahren, die erläutert werden.  
  
## Siehe auch  
 [OLE\-Hintergrund](../mfc/ole-background.md)   
 [Container: Implementieren eines Containers](../mfc/containers-implementing-a-container.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md)