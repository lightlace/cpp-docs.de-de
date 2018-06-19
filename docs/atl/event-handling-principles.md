---
title: Prinzipien (ATL) für die Ereignisbehandlung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb7577dc7d9fb58f43ee67d5e5b8f00393dca1bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355447"
---
# <a name="event-handling-principles"></a>Ereignis Behandlung Prinzipien
Es gibt drei Schritte, die alle Ereignisbehandlung gemeinsam. Sie müssen:  
  
-   Implementieren Sie die Schnittstelle für das Objekt.  
  
-   Informieren Sie der Ereignisquelle, Ihr Objekt Ereignisse empfangen möchte.  
  
-   Die Ereignisquelle senkereigniszuordnung, wenn Ihr Objekt nicht mehr benötigt wird, um Ereignisse zu empfangen.  
  
 Seinen Typ hängt von der Möglichkeit, dass Sie die Schnittstelle implementieren. Eine Ereignisschnittstelle möglich Vtable, Dual oder eine Dispinterface. Es liegt an den Designer der Ereignisquelle zum Definieren der Schnittstelle; Es liegt an Ihnen, diese Schnittstelle implementieren.  
  
> [!NOTE]
>  Es gibt, zwar keine aus technischen Gründen, die eine Ereignisschnittstelle duale sein kann stehen eine Reihe von Gründen guten Entwurf, um die Verwendung der Entwurfssicht zu vermeiden. Dies ist jedoch eine Entscheidung wurde absichtlich getroffen, die vom Designer/Implementierer des Ereignisses *Quelle*. Da Sie aus der Perspektive des Ereignisses arbeiten `sink`, müssen Sie die Möglichkeit zu ermöglichen, dass Sie keiner Wahl haben, können jedoch eine duale Ereignisschnittstelle zu implementieren. Weitere Informationen zu duale Schnittstellen, finden Sie unter [duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md).  
  
 Anmelden der Ereignisquelle kann in drei Schritte unterteilt werden:  
  
-   Das Quellobjekt für Abfragen [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   Rufen Sie [IConnectionPointContainer:: FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) übergeben Sie die IID der Ereignisschnittstelle, die Sie interessieren. Wenn erfolgreich, dieser zurückgibt, die [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) Schnittstelle für ein Objekt.  
  
-   Rufen Sie [IConnectionPoint:: Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) übergeben der **IUnknown** der Ereignissenke. Wenn erfolgreich, dies Zurückgeben einer `DWORD` Cookie, das die Verbindung darstellt.  
  
 Nachdem Sie Ihr Interesse an der Empfang von Ereignissen erfolgreich registriert haben, werden Methoden für Ereignisschnittstelle des Objekts entsprechend den Ereignissen, die ausgelöst wird, indem das Quellobjekt, das aufgerufen werden. Wenn Sie sich nicht mehr benötigen, die zum Empfangen von Ereignissen, können Sie das Cookie übergeben, über dem Verbindungspunkt an [IConnectionPoint:: Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608). Dadurch wird die Verbindung zwischen Quelle und Senke unterbrochen.  
  
 Achten Sie darauf, dass Sie vermeiden Zyklen, wenn Sie Ereignisse behandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)

