---
title: DCOM-Geschichte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation, DCOM
- DCOM, about DCOM
- DCOM
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ef567c39c93c3d43fdfc0fa63886144b03cd474
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="history-of-dcom"></a>DCOM-Geschichte
Wenn Automation in frühen 1993 erstmals eingeführt wurde, konnte es nur zwischen auf dem gleichen Computer ausgeführten Anwendungen verwendet wird. Jedoch, da er gemeinsam die gleichen Grundlagen wie der Rest des OLE, die COM-(oder Component Object Model), wurde sie immer vorgesehen, dass er "remotefähige" werden würde, wenn COM selbst aktualisiert wurde, dass Remotefunktionen enthalten. Es wurde auch geplant, dass der Übergang von ausschließlich lokalen Vorgang zur verteilten Vorgang nur wenig oder gar keine Änderungen am vorhandenen Code erfordert.  
  
 Damit "Remoting" lokale COM Bedeutung vorgegeben, dass der Consumer einer Schnittstelle befinden, und führen Sie auf dem gleichen Computer wie der Anbieter dieser Schnittstelle. Z. B. Microsoft Visual Basic können eine Kopie von Microsoft Excel auf dem Desktopcomputer steuern, aber es war nicht kann die Ausführung von Excel auf einem anderen Computer weitergeleitet. Mit der Entwicklung von distributed COM muss der Consumer einer Schnittstelle nicht mehr auf dem gleichen Computer wie die befinden, auf denen der Schnittstelle-Anbieter ausgeführt wird.  
  
 Sobald COM arbeiten in einem Netzwerk angepasst wurde, klicken Sie dann jede Schnittstelle, die nicht mit einem Modell für die lokale Ausführung gebunden wurde (einige Schnittstellen sind inhärenten Abhängigkeit von der lokalen Funktionen, wie z. B. die Schnittstellen zeichnen, deren Methoden verfügen über Handles für Gerätekontexte als Parameter), müsste die Möglichkeit, verteilt werden. Ein Schnittstelle Consumer würde eine Anforderung für eine bestimmte Schnittstelle zu erstellen; Diese Schnittstelle kann von einer Instanz eines Objekts ausgeführt wird (oder auszuführenden) auf einem anderen Computer bereitgestellt werden. Verteilungsmechanismus innerhalb COM verbinden den Consumer an den Anbieter so, dass Methodenaufrufe, die vom Consumer am Ende Anbieter angezeigt werden würden, würden sie ausgeführt werden. Rückgabewert, dass die Werte dann zurück an den Consumer gesendet werden. Zu Verteilungsvorgang, dient die Verteilung für den Consumer und der Anbieter transparent.  
  
 Solche eine Vielzahl von COM ist jetzt vorhanden. DCOM (für "distributed COM") wurde mit Versionen von Windows NT ab Version 4.0 und einschließlich Windows 2000 geliefert. Spät es wurde auch seit 1996, verfügbar für Windows 9 X. In beiden Fällen umfasst DCOM einen Satz von Ersatz und zusätzliche DLLs mit einige Hilfsprogramme, die sowohl lokale als auch COM-Funktionen bereitstellen. Es ist daher jetzt ein fester Bestandteil der Win32-basierten Plattformen und wird verfügbar gemacht werden auf anderen Plattformen die andere Organisationen über die Zeit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Wann ist Remoteautomatisierung angebracht](where-does-remote-automation-fit-in-q.md)  
  
 [Welche Vorteile Remoteautomatisierung](what-does-remote-automation-provide-q.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)
