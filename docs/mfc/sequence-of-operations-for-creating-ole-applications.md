---
title: "Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen"
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
  - "Anwendungen [OLE]"
  - "Anwendungen [OLE], Erstellen"
  - "OLE-Anwendungen [C++]"
  - "OLE-Anwendungen [C++], Erstellen"
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle wird die Rolle und die Rolle des Frameworks an, wenn dieser erstellt OLE, das verknüpft und Anwendungen eingebettet werden.  Diese stellen die Optionen dar, sondern als eine Sequenz von Schritten, um auszuführen verfügbar sind.  
  
### Erstellen von OLE\-Anwendungen  
  
|Aufgabe|Hierzu|Das Framework führt|  
|-------------|------------|-------------------------|  
|Erstellen Sie eine COM\-Komponente.|Führen Sie den MFC\-Anwendungs\-Assistenten aus.  Wählen Sie **Vollserver** oder **Miniserver** auf der Registerkarte **Verbunddokumente** aus.|Das Framework generiert ein Anwendungsskelett mit aktivierter COM\-Komponenten\-Funktion.  Alle COM\-Funktion kann in der vorhandenen Anwendung mit lediglich Leistung Änderung übertragen werden.|  
|Erstellen Sie eine Containeranwendung von Grund auf neu.|Führen Sie den MFC\-Anwendungs\-Assistenten aus.  Wählen Sie **Container** auf der Registerkarte **Verbunddokumente** aus.  Verwenden der Klassenansicht in den Quellcode\-Editor.  Füllen Sie Code für die COM\-Handlerfunktionen aus.|Das Framework generiert ein Anwendungsskelett, das die COM\-Objekte einfügen kann, die mithilfe erstellt werden Anwendungen der COM\-Komponente \(Server\).|  
|Erstellen Sie eine Anwendung, die Automatisierung von Grund auf neu unterstützt.|Führen Sie den MFC\-Anwendungs\-Assistenten aus.  Wählen Sie **Automatisierung** aus der Registerkarte **Erweiterte Funktionen** aus.  Verwenden Sie die Klassenansicht, um Methoden und Eigenschaften in der Anwendung für Automatisierung verfügbar zu machen.|Das Framework generiert ein Anwendungsskelett, das von anderen Anwendungen aktiviert und automatisiert werden kann.|  
  
## Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC\-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Operationssequenz zur Erstellung von ActiveX\-Steuerelementen](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)