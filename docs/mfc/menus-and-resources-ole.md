---
title: "Men&#252;s und Ressourcen (OLE)"
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
  - "Anwendungen [OLE], Menüs und Ressourcen"
  - "Container [C++], OLE-Containeranwendungen"
  - "Direkte Aktivierung, OLE-Menüs und Ressourcen"
  - "Menüs [C++], OLE-Dokumentanwendungen"
  - "OLE-Anwendungen [C++], Menüs und Ressourcen"
  - "OLE-Container, Menüs und Ressourcen"
  - "OLE-Menüs und Ressourcen"
  - "OLE-Serveranwendungen, Menüs und Ressourcen"
  - "OLE-Server für visuelle Bearbeitung"
  - "Serveranwendungen, OLE-Menüs und Ressourcen"
  - "Statusleisten, OLE-Dokumentanwendungen"
  - "Zeichenfolgenbearbeitung, Anwendungen für visuelle Bearbeitung"
  - "Zeichenfolgentabellen, Anwendungen für visuelle Bearbeitung"
  - "Symbolleisten [C++], OLE-Dokumentanwendungen"
  - "Visuelle Bearbeitung, Anwendungsmenüs und Ressourcen"
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Men&#252;s und Ressourcen (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Gruppe Artikel erklärt die Verwendung von Menüs und Ressourcen in MFC\-OLE dokumentieren Anwendungen.  
  
 Zusätzliche Anforderungen der Stellen der visuellen Bearbeitungen im OLE im Menü und anderen Ressourcen, die in OLE bereitgestellt werden, dokumentieren Anwendungen, da es mehrere Modi gibt, in denen Server\(Container\- und Komponente\) Anwendungen gestartet werden kann.  Beispielsweise kann eine FULLServer\-Anwendung in alle drei Modi ausgeführt werden:  
  
-   Eigenständig.  
  
-   Vorhanden zum Bearbeiten eines Elements im Kontext einem Container.  
  
-   Öffnen, zum Bearbeiten eines Elements nicht im Rahmen seines Containers, oftmals in einem separaten Fenster.  
  
 Dies erfordert drei verschiedene Menülayouts, eines für jeden Modus der Anwendung.  Zugriffstastentabellen sind auch für jeden neuen Modus erforderlich.  Eine Containeranwendung unterstützt möglicherweise direkte Aktivierung; wenn ja, benötigt sie eine neue Menüstruktur und zugeordneten Zugriffstastentabellen.  
  
 Direkte Aktivierung erforderlich, dass der Container und die für Serveranwendungen Menü, Symbolleiste und Statusleistenabstand aushandeln müssen.  Alle Ressourcen müssen in diesem Sinne entworfen.  Der Artikel [Menüs und Ressourcen: Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md) enthält dieses Thema detailliert.  
  
 Aufgrund dieser Probleme können die OLE\-Dokument\-Anwendungen, die mit dem Anwendungs\-Assistenten erstellt werden, bis vier verschiedene Menüs und Zugriffstastentabellenressourcen haben.  Diese werden für die folgenden Gründe verwendet:  
  
|Ressourcenname|Verwendung|  
|--------------------|----------------|  
|**IDR\_MAINFRAME**|Wird in einer MDI\-Anwendung, wenn keine Datei geöffnet oder in einer SDI\-Anwendung unabhängig davon geöffnete Dateien.  Dies ist das Standardmenü, das in den Anwendungen NichtOLE verwendet wird.|  
|**IDR\_projectTYPE \<\>**|Wird in einer MDI\-Anwendung, wenn Dateien geöffnet sind.  Wird verwendet, wenn eine Anwendung ausgeführt eigenständig ist.  Dies ist das Standardmenü, das in den Anwendungen NichtOLE verwendet wird.|  
|**\<\>IDR\_projectTYPE\_SRVR\_IP**|Wird vom Server oder den Container, wenn ein Objekt geöffnet gesorgt ist.|  
|**\<\>IDR\_projectTYPE\_SRVR\_EMB**|Wird von einer Serveranwendung, wenn ein Objekt geöffnet, ohne direkte Aktivierung zu verwenden.|  
  
 Jeder dieser Ressourcennamen stellt ein Menü und normalerweise eine Zugriffstastentabelle dar.  Ein Ähnliches Schema sollte in MFC\-Anwendungen verwendet werden, die nicht mit dem Anwendungs\-Assistenten erstellt werden.  
  
 Die folgenden Elemente werden die Themen, die den Containern, auf den Servern und die Menüzusammenführung erforderlich, direkte Aktivierung implementieren verknüpft werden:  
  
-   [Menüs und Ressourcen: Container\-Hinzufügungen](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menüs und Ressourcen: Server\-Hinzufügungen](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menüs und Ressourcen: Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md)  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)