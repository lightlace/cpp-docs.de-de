---
title: Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee0fd14e2e2d87155bfafefca6fa17e1d77135f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375384"
---
# <a name="servers"></a>Server

Ein Server-Anwendung (oder die Komponente-Anwendung) erstellt OLE Elemente (oder Komponenten) für die Verwendung von containeranwendungen. Eine visuelle Bearbeitung Serveranwendung unterstützt auch die visuelle Bearbeitung oder direkte Aktivierung. Eine andere Form der OLE-Server ist ein [Automatisierungsserver](../mfc/automation-servers.md). Einige serveranwendungen unterstützen nur die Erstellung der eingebetteten Elemente. andere unterstützen die Erstellung von eingebettete und verknüpfte Ressourcen. Einige unterstützen nur das verknüpfen, obwohl dies selten ist. Alle serveranwendungen müssen Aktivierung von containeranwendungen unterstützen, wenn der Benutzer ein Element bearbeiten möchte. Eine Anwendung kann es sich um einen Container und ein Server sein. Das heißt, kann es sowohl Daten einbeziehen, in dessen Dokumente, und erstellen Daten, die als Elemente in Dokumenten mit anderen Anwendungen integriert werden können.

Ein Miniserver ist eine besondere Art von Serveranwendung, die nur von einem Container gestartet werden kann. Microsoft Draw und Microsoft Graph sind Beispiele für Miniserver. Ein Miniserver werden Dokumente nicht als Dateien auf dem Datenträger gespeichert werden. Stattdessen liest seine Dokumente aus, und schreibt sie in der Elemente in Dokumenten, die zu dem Container gehören wird. Daher unterstützt ein Miniserver einbetten, nicht verknüpfen.

Ein vollständiger Server kann entweder als eigenständige Anwendung ausgeführt oder von einer containeranwendung gestartet werden. Ein vollständiger Server kann Dokumente als Dateien auf dem Datenträger speichern. Es kann unterstützen nur die Einbettung, beide einbetten und verknüpfen oder Verknüpfung nur. Der Benutzer eine containeranwendung kann ein eingebettetes Element erstellen, indem Sie auf den Befehl zum Ausschneiden oder Kopieren der Server und den Befehl "Einfügen" im Container. Ein verknüpftes Element wird erstellt, indem Sie auf den Befehl Kopieren, auf dem Server und den einfügen-Link-Befehl des Containers. Alternativ kann der Benutzer ein eingebettetes oder verknüpftes Element, das über das Dialogfeld "Objekt einfügen" erstellen.

In der folgende Tabelle werden die Eigenschaften verschiedener Typen von Servern zusammengefasst:

### <a name="server-characteristics"></a>Servereigenschaften

|Typ des Servers|Unterstützt mehrere Instanzen|Elemente pro Dokument|Dokumente pro Instanz|
|--------------------|---------------------------------|------------------------|----------------------------|
|Miniserver|Ja|1|1|
|SDI-Vollserver|Ja|1 (wenn verknüpfen unterstützt wird, 1 oder mehr)|1|
|MDI-Vollserver|Nein (nicht erforderlich)|1 (wenn verknüpfen unterstützt wird, 1 oder mehr)|0 oder mehr|

Eine Server-Anwendung sollte mehrere Container gleichzeitig unterstützen, die mehr als ein Container mit der ein eingebettetes oder verknüpftes Element zu bearbeiten. Wenn der Server eine SDI-Anwendung (oder ein Miniserver mit einem Dialogfeld-) ist, müssen mehrere Instanzen des Servers gleichzeitig ausgeführt werden können. Dadurch wird eine separate Instanz der Anwendung, jeder Container-Anforderung zu verarbeiten.

Wenn der Server eine MDI-Anwendung ist, können sie einen neuen untergeordneten MDI-Fensters jedes Mal erstellen ein Container ein Element zu bearbeiten muss. Auf diese Weise kann eine einzelne Instanz der Anwendung mehrere Container unterstützen.

Die Server-Anwendung muss der OLE-System-DLLs erläutert, wie bei einer Instanz von dem Server bereits ausgeführt wird, wenn ein anderer Container seine Dienste anfordert mitteilen: Gibt an, ob sie eine neue Instanz des Servers zu starten oder leitet Anforderungen von allen Containern mit einer Instanz von sollte die Server.

Weitere Informationen zu Servern finden Sie unter:

- [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)

- [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md)

- [Server: Implementieren eines In-Place-Frame-Fensters](../mfc/servers-implementing-in-place-frame-windows.md)

- [Server: Serverelemente](../mfc/servers-server-items.md)

- [Server: Probleme mit der Benutzeroberfläche](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[Container](../mfc/containers.md)<br/>
[Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)<br/>
[Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Registrierung](../mfc/registration.md)<br/>
[Automatisierungsserver](../mfc/automation-servers.md)

