---
title: 'OLE-Hintergrund: Container und Server | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f15ef532ba61a089f8adec9ed20f737c07eae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348546"
---
# <a name="ole-background-containers-and-servers"></a>OLE-Hintergrund: Container und Server
Eine Steuerelementcontainer-Anwendung ist eine Anwendung, die eingebettete oder verknüpfte Elemente in einem eigenen Dokumente integrieren kann. Die Dokumente, die von einem Steuerelementcontainer-Anwendung verwaltet müssen speichern und Anzeigen von Komponenten der OLE-Dokumente als auch die Daten, die von der Anwendung selbst erstellt werden. Eine Steuerelementcontainer-Anwendung muss auch Benutzern neue Elemente eingefügt oder Bearbeiten von vorhandenen Elementen von serveranwendungen, die bei Bedarf zu aktivieren. Die Benutzeroberfläche Anforderungen eine Steuerelementcontainer-Anwendung im Artikel aufgelisteten [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md).  
  
 Eine Server-Anwendung oder Komponente Anwendung ist eine Anwendung, die zur Verwendung von Komponenten Dokument OLE-containeranwendungen erstellen kann. Server-Anwendungen unterstützen normalerweise ziehen und Ablegen oder ihre Daten in die Zwischenablage kopieren, damit, dass eine Steuerelementcontainer-Anwendung die Daten als eingebettete oder verknüpfte Element eingefügt werden kann. Eine Anwendung kann es sich um einen Container und einem Server sein.  
  
 Die meisten Server sind eigenständige Anwendungen oder vollständigen Server; Sie können entweder als eigenständige Anwendungen ausgeführt werden oder können durch eine Steuerelementcontainer-Anwendung gestartet werden. Ein Miniserver ist eine besondere Art von Server-Anwendung, die nur von einem Container gestartet werden kann. Es kann nicht als eigenständige Anwendung ausgeführt werden. Microsoft Draw und Microsoft Graph sind Beispiele für Miniserver.  
  
 Container und Server kommunizieren nicht direkt. Stattdessen kommuniziert, über die OLE-System Dynamic Link Libraries (DLL). Diese DLLs bieten Funktionen, die Container und Server aufrufen und die Container und Server bieten Fehlerrückruf-Funktionen, die die DLLs aufrufen.  
  
 Verwenden diese Art der Kommunikation, muss ein Container nicht wissen, die Implementierungsdetails der Server-Anwendung. Sie können einen Container zum Akzeptieren von Elementen, die von einem beliebigen Server erstellt werden, ohne die Typen von Servern zu definieren, mit denen sie arbeiten kann. Daher kann der Benutzer eine Steuerelementcontainer-Anwendung zukünftige Anwendungen und Datenformate nutzen. Wenn diese neue Anwendungen OLE-Komponenten sind, wird ein Verbunddokument Elemente erstellt, durch die Anwendung integrieren können.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE-Hintergrund](../mfc/ole-background.md)   
 [OLE-Hintergrund: MFC-Implementierung](../mfc/ole-background-mfc-implementation.md)   
 [Containers](../mfc/containers.md)   
 [Server](../mfc/servers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)

