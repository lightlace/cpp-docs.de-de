---
title: Wann ist Remoteautomatisierung angebracht? | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ad6eef0bbaad7860e7f4310ce283efe18c668eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="where-does-remote-automation-fit-in"></a>Wann ist Remoteautomatisierung angebracht?
DCOM 1996 veröffentlicht wurde, und ist mit 32-Bit und 64-Bit-Plattformen verfügbar. Visual Basic-Team bei Microsoft hat Visual Basic als mithilfe der Automatisierung um seiner Komponenten für die Kommunikation zu ermöglichen immer sichtbar. Das Fehlen einer verteilten Version begrenzt die Verwendung dieser Funktionen in Enterprise-Umgebungen schwerwiegend ist, das Team, das Entwickeln von Visual Basic 4.0 Enterprise Edition entschieden, einen eigenen Satz von Remoting-Komponenten für die Automatisierung die Erstellung untersuchen Teile des OLE und COM. Ein Hauptziel war klar, stellen Sie sicher, dass das Ergebnis mit kompatibel wäre und von DCOM ersetzt werden, kann wenn er verfügbar ist. Sie optimiert dann Remote Automatisierung (RA) für 16-Bit- und 32-Bit-Windows-Plattformen zu implementieren.  
  
 Remoteautomatisierung ist nicht in eine bestimmte Sprache gebunden, aber bis zur Freigabe von Enterprise-Edition von Visual C++ 4.2, es nur mit Visual Basic 4.0 geliefert wurde. Bedenken Sie, dass Remoteautomatisierung vollständig von DCOM klassifiziert wird. Wenn Sie die Möglichkeit DCOM anstelle von Remoteautomatisierung in Ihren Anwendungen verwendet haben, sollten Sie dies tun. Es gibt dennoch Szenarien, in denen Remoteautomatisierung besser geeignet ist:  
  
-   Dort haben Sie 16-Bit-Clients.  
  
-   Wenn Ihre Organisation keiner DCOM-aktivierten Version von Windows NT oder Windows 95 noch ein Rollback ausgeführt wurde.  
  
-   Wenn ein eine vorhandenen Anwendungssuite Upgrade verwendet, Remoteautomatisierung für C++-Komponenten verwenden, statt eine oder mehrere Komponenten von Visual Basic.  
  
 Es müssen keinen Unterschied zwischen Programmen, die Remoteautomatisierung sowie die Verwendung von Automatisierung über DCOM erstellten Verwendung erstellt werden, und die Konfigurationsprogramme können sehr einfach Remoteautomatisierung und DCOM-Operation zu wechseln. Daher ist es nicht schwer zu eine Anwendung Remoteautomatisierung DCOM aktualisieren, nachdem die Infrastruktur vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Welche Vorteile Remoteautomatisierung](what-does-remote-automation-provide-q.md)   
 [DCOM-Geschichte](../mfc/history-of-dcom.md)
