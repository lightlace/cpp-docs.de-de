---
title: "Server"
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
  - "Vollserver"
  - "Miniserver"
  - "OLE-Serveranwendungen"
  - "OLE-Serveranwendungen, Aktivierung"
  - "OLE-Serveranwendungen, Servertypen"
  - "Serveranwendungen"
  - "Server"
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Serveranwendung \(oder Teil\-Anwendung\) erstellt OLE\-Elemente \(oder Komponenten\) für Containeranwendungen.  Eine visuelle Bearbeitung unterstützt außerdem visuelle Bearbeitung oder direkte Aktivierung.  Eine andere Form von OLE\-Server ist [Automatisierungsserver](../mfc/automation-servers.md).  Einige Serveranwendungen unterstützen nur die Erstellung von eingebetteten Elemente; andere unterstützen die Erstellung von eingebetteten und verknüpften Elementen.  Einige unterstützen nur verknüpfen, obwohl dies selten ist.  Alle Serveranwendungen müssen Aktivierung durch Containeranwendungen unterstützen, wenn der Benutzer ein Element bearbeiten möchte.  Eine Anwendung kann ein Container und ein Server sein.  Das bedeutet, dass es Daten in die Dokumente enthalten erstellt und Daten, die als Elemente in die Dokumente anderer Anwendungen integriert werden können.  
  
 Ein miniserver ist ein spezieller Typ Serveranwendung, der durch einen Container nur gestartet werden kann.  Microsoft zeichnen und Microsoft Graph sind Beispiele für miniservers.  Ein miniserver speichert Dokumente nicht als Dateien auf einem Datenträger.  Stattdessen liest er die Dokumente aus und schreibt sie an Elemente in Dokumente, in Containern gehören.  Demzufolge unterstützt ein miniserver nur einbetten und nicht verknüpft.  
  
 Ein voller Server kann entweder als eigenständige Anwendung ausgeführt oder durch eine Containeranwendung gestartet werden.  Ein voller Server können Dokumente als Dateien auf einem Datenträger speichern.  Er kann nur einbetten unterstützen, das Einbetten und Verknüpfen oder nur verknüpfen.  Der Benutzer einer Containeranwendung kann ein eingebettetes Element erstellen, indem er über die Befehle Ausschneiden oder Kopierbefehl im Server und den Befehl Einfügen im Container auswählt.  Ein verlinktes Element wird erstellt, indem den Kopierbefehl im Server und den Pasten\-Linkbefehl im Container auswählt.  Alternativ kann der Benutzer ein verknüpftes oder eingebettetes Element mithilfe des EINFG\-Objektdialogfelds erstellen.  
  
 In der folgenden Tabelle werden Eigenschaften verschiedener Typen der Server zusammen:  
  
### Server\-Eigenschaften  
  
|Typ des Servers|Unterstützt mehrere Instanzen|Elemente pro Dokument|Dokumente pro Instanz|  
|---------------------|-----------------------------------|---------------------------|---------------------------|  
|Miniserver|ja|1|1|  
|Vollständiger SDI Server|ja|1 \(bei Verknüpfen unterstützt wird, 1 oder mehr\)|1|  
|Vollständiger MDI Server|Keine \(nicht erforderlich\)|1 \(bei Verknüpfen unterstützt wird, 1 oder mehr\)|0 oder mehr|  
  
 Eine Anwendung sollte mehrere Container gleichzeitig unterstützt, im Fall, dass mehr als ein Container verwendet wird, um ein verknüpftes oder eingebettetes Element zu manipulieren.  Wenn der Server eine SDI\-Anwendung \(oder ein miniserver mit einer Dialogfeldschnittstelle\) handelt, müssen mehrere Instanzen des Servers in der Lage sein, gleichzeitig ausgeführt werden.  Dies ermöglicht eine separate Instanz der Anwendung, jede Containeranforderung zu bearbeiten.  
  
 Wenn der Server eine MDI\-Anwendung ist, kann er ein neues untergeordnetes MDI\-Fenster erstellen, wenn ein Container ein Element manipulieren muss.  Auf diese Weise kann eine einzelne Instanz der Anwendung mehrere Container unterstützen.  
  
 die Serveranwendung muss den OLE\-System\-DLLs was mitteilen auszuführen, wenn eine Instanz des Servers bereits ausgeführt wird, wenn ein anderer Container seine Dienste müssen: ob eine neue Instanz des Servers starten oder die Anforderungen aller Container auf eine Instanz des Servers verweisen soll.  
  
 Ausführliche Informationen auf Servern, finden Sie unter:  
  
-   [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)  
  
-   [Server: Implementieren von Server\-Dokumenten](../mfc/servers-implementing-server-documents.md)  
  
-   [Server: Implementieren der direkten Rahmenfenstern](../mfc/servers-implementing-in-place-frame-windows.md)  
  
-   [Server: Serverelemente](../mfc/servers-server-items.md)  
  
-   [Server: Benutzeroberfläche\-Probleme](../mfc/servers-user-interface-issues.md)  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Container](../mfc/containers.md)   
 [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)   
 [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Registrierung](../mfc/registration.md)   
 [Automatisierungsserver](../mfc/automation-servers.md)