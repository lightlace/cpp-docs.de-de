---
title: 'OLE-Hintergrund: Container und Server | Microsoft-Dokumentation'
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
ms.openlocfilehash: 23aa5e4c13e8049a2240462dab1c5b68bfb514f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436935"
---
# <a name="ole-background-containers-and-servers"></a>OLE-Hintergrund: Container und Server

Eine Container-Anwendung ist eine Anwendung, die eingebettete oder verknüpfte Elemente in ihre eigenen Dokumente integrieren kann. Die Dokumente, die von einer Anwendung mit Containern verwalteten muss speichern und Anzeigen von Komponenten des OLE-Dokumente als auch die Daten, die von der Anwendung selbst erstellt. Eine Container-Anwendung muss auch Benutzern neue Elemente einfügen oder bearbeiten vorhandene Elemente von Server-Anwendungen bei Bedarf zu aktivieren. Die Anforderungen der Benutzeroberfläche einer Container-Anwendung finden Sie im Artikel [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md).

Ein Server-Anwendung oder Komponente-Anwendung ist eine Anwendung, die Komponenten des OLE-Dokumente für die Verwendung von containeranwendungen erstellen können. In der Regel Unterstützung von serveranwendungen Drag & Drop oder kopieren ihre Daten in die Zwischenablage, sodass eine Container-Anwendung die Daten als ein eingebettetes oder verknüpftes Element einfügen kann. Eine Anwendung kann es sich um einen Container und ein Server sein.

Die meisten Server sind eigenständige Anwendungen oder vollständige Server. Sie können entweder als eigenständige Anwendungen ausgeführt werden oder können mit einer containeranwendung gestartet werden. Ein Miniserver ist eine besondere Art von Serveranwendung, die nur von einem Container gestartet werden kann. Es kann nicht als eigenständige Anwendung ausgeführt werden. Microsoft Draw und Microsoft Graph-Server sind Beispiele für Miniserver.

Container und Server kommunizieren nicht direkt. Stattdessen kommunizieren sie über die OLE-System Dynamic Link Libraries (DLL). Diese DLLs bieten Funktionen, die Container und Server aufrufen und den Container und Server bieten Rückruffunktionen, die die DLLs aufrufen.

Verwenden diese Art der Kommunikation, muss ein Container nicht wissen, die Implementierungsdetails der Server-Anwendung. Sie können einen Container zum Akzeptieren von Elementen, die von einem beliebigen Server erstellt werden, ohne die Typen von Servern zu definieren, mit denen sie arbeiten kann. Daher kann der Benutzer einer containeranwendung zukünftige Anwendungen und Datenformate nutzen. Wenn diese neuen Anwendungen OLE-Komponenten sind, wird ein Verbunddokument Elemente erstellt, die von diesen Anwendungen integrieren können.

## <a name="see-also"></a>Siehe auch

[OLE-Hintergrund](../mfc/ole-background.md)<br/>
[OLE-Hintergrund: MFC-Implementierung](../mfc/ole-background-mfc-implementation.md)<br/>
[Container](../mfc/containers.md)<br/>
[Server](../mfc/servers.md)<br/>
[Container: Clientelemente](../mfc/containers-client-items.md)<br/>
[Server: Serverelemente](../mfc/servers-server-items.md)

