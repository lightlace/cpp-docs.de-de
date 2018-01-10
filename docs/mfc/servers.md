---
title: Server | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0a011201a521ed97cf9ebe4c0a8249526b9d7c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="servers"></a>Server
Eine Serveranwendung (oder Component-Anwendung) erstellt OLE Elemente (oder Komponenten) für die Verwendung von containeranwendungen. Eine visuelle Bearbeitung Serveranwendung unterstützt auch die visuelle Bearbeitung oder direkte Aktivierung. Eine andere Form der OLE-Server ist ein [Automatisierungsservers](../mfc/automation-servers.md). Für einige serveranwendungen unterstützt nur die Erstellung der eingebetteten Elemente. andere Anbieter unterstützen die Erstellung von eingebettete und verknüpfte Ressourcen. Einige unterstützen nur das verknüpfen, obwohl dies nur selten auftritt. Alle serveranwendungen müssen Aktivierung von containeranwendungen unterstützen, wenn der Benutzer ein Element bearbeiten möchte. Eine Anwendung kann es sich um einen Container und einem Server sein. Das heißt, kann Daten, die als Elemente in anderen Dokumenten integriert werden können sie beide Integrieren von Daten in ihre Dokumente und erstellen zu.  
  
 Ein Miniserver ist eine besondere Art von Server-Anwendung, die nur von einem Container gestartet werden kann. Microsoft Draw und Microsoft Graph sind Beispiele für Miniserver. Ein Miniserver werden Dokumente nicht als Dateien auf dem Datenträger gespeichert werden. Stattdessen werden seine Dokumente aus liest und schreibt sie in Elemente in Dokumenten, die zu dem Container gehören. Daher unterstützt ein Miniserver nur die Einbettung, nicht verknüpfen.  
  
 Ein vollständiger Server kann ausführen, entweder als eigenständige Anwendung oder durch eine Steuerelementcontainer-Anwendung gestartet werden. Ein vollständiger Server kann Dokumente als Dateien auf dem Datenträger speichern. Es kann nur die Einbettung, beide Einbetten von und verknüpfen oder Verknüpfung nur unterstützen. Der Benutzer eine Steuerelementcontainer-Anwendung kann ein eingebettetes Element erstellen, indem Sie den Befehl Ausschneiden oder Kopieren in den Server und den Befehl "Einfügen" im Container auswählen zu können. Ein verknüpftes Element wird erstellt, indem Sie den Kopierbefehl auf dem Server und den einfügen-Link-Befehl im Container auswählen. Alternativ kann der Benutzer eine eingebettete oder verknüpfte Element, über das Dialogfeld "Objekt einfügen" erstellen.  
  
 Die folgende Tabelle fasst die Merkmale verschiedener Typen von Servern:  
  
### <a name="server-characteristics"></a>Servereigenschaften  
  
|Typ des Servers|Unterstützt mehrere Instanzen|Elemente pro Dokument|Dokumente pro Instanz|  
|--------------------|---------------------------------|------------------------|----------------------------|  
|Miniserver|Ja|1|1|  
|Vollständige SDI-server|Ja|1 (wenn verknüpfen unterstützt wird, 1 oder mehr)|1|  
|Vollständige MDI-server|Nein (nicht erforderlich)|1 (wenn verknüpfen unterstützt wird, 1 oder mehr)|0 oder mehr|  
  
 Eine Serveranwendung sollten mehrere Container gleichzeitig unterstützen, wenn mehr als ein Container so bearbeiten Sie eine eingebettete oder verknüpfte Element verwendet wird. Wenn der Server eine SDI-Anwendung (oder ein Miniserver mit einem Dialogfenstern) ist, müssen mehrere Instanzen des Servers gleichzeitig ausgeführt werden können. Dadurch wird eine separate Instanz von der Anwendung zur Handhabung von jeder Container-Anforderung.  
  
 Wenn der Server eine MDI-Anwendung ist, können sie ein neues untergeordnetes MDI-Fenster erstellen, ein Container ein Element zu bearbeiten muss. Auf diese Weise kann eine einzelne Instanz der Anwendung mehrere Container unterstützen.  
  
 Die Server-Anwendung muss der OLE-System-DLLs erläutert, wie bei einer Instanz des Servers bereits ausgeführt wird, wenn eine andere Container, seine Dienste anfordert mitteilen: Gibt an, ob diese starten Sie einer neuen Instanz des Servers oder leiten alle Container-Anforderungen an eine Instanz des sollte die Server.  
  
 Weitere Informationen zu Servern finden Sie unter:  
  
-   [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)  
  
-   [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)  
  
-   [Server: Implementieren eines In-Place-Frame-Fensters](../mfc/servers-implementing-in-place-frame-windows.md)  
  
-   [Server: Serverelemente](../mfc/servers-server-items.md)  
  
-   [Server: Probleme mit der Benutzeroberfläche](../mfc/servers-user-interface-issues.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Containers](../mfc/containers.md)   
 [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)   
 [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)   
 [Registrierung](../mfc/registration.md)   
 [Automatisierungsserver](../mfc/automation-servers.md)

