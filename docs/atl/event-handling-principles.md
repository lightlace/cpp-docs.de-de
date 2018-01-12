---
title: "Prinzipien (ATL) für die Ereignisbehandlung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6ec61751e16bd67686a983b43c79fea138b3fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

