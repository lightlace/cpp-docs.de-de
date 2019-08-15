---
title: Ereignis Behandlungsprinzipien (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 066c8db60afed31ceba1c9ef6f4a10d5f842e608
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492145"
---
# <a name="event-handling-principles"></a>Grundlagen der Ereignis Behandlung

Es gibt drei Schritte, die bei der Ereignis Behandlung üblich sind. Folgendes ist erforderlich:

- Implementieren Sie die-Ereignis Schnittstelle für das-Objekt.

- Informieren Sie die Ereignis Quelle, dass Ihr Objekt Ereignisse empfangen möchte.

- Deaktivieren Sie die Ereignis Quelle, wenn das Objekt keine Ereignisse mehr empfangen muss.

Die Art und Weise, in der die Ereignis Schnittstelle implementiert wird, hängt vom Typ ab. Eine Ereignis Schnittstelle kann "Vtable", "Dual" oder "dispinterface" sein. Es liegt an dem Designer der Ereignis Quelle, die Schnittstelle zu definieren. Sie müssen diese Schnittstelle implementieren.

> [!NOTE]
>  Obwohl es keine technischen Gründe gibt, dass eine Ereignis Schnittstelle nicht Dual sein kann, gibt es eine Reihe guter Entwurfs Gründe, um die Verwendung von Duals zu vermeiden. Dies ist jedoch eine Entscheidung, die vom Designer/Implementierer der Ereignis *Quelle*getroffen wird. Da Sie aus der Perspektive des Ereignisses `sink`arbeiten, müssen Sie möglicherweise keine Auswahl treffen, sondern eine Dual-Event-Schnittstelle implementieren. Weitere Informationen zu Dual Schnittstellen finden Sie unter [duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md).

Die Beratung der Ereignis Quelle kann in drei Schritte unterteilt werden:

- Abfragen des Quell Objekts für [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Nennen Sie [IConnectionPointContainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) , indem Sie die IID der Ereignis Schnittstelle übergeben, die Sie interessiert. Bei erfolgreicher Ausführung wird die [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) -Schnittstelle für ein Verbindungspunkt Objekt zurückgegeben.

- Wenden Sie [IConnectionPoint:: Rat](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) an `IUnknown` , und übergeben Sie die der Ereignis Senke. Bei erfolgreicher Ausführung wird ein `DWORD` Cookie zurückgegeben, das die Verbindung darstellt.

Nachdem Sie Ihr Interesse am Empfang von Ereignissen erfolgreich registriert haben, werden die Methoden der Ereignis Schnittstelle Ihres Objekts entsprechend den Ereignissen aufgerufen, die vom Quell Objekt ausgelöst werden. Wenn Sie keine Ereignisse mehr empfangen müssen, können Sie das Cookie über [IConnectionPoint:: UN-Empfehlung](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)an den Verbindungspunkt zurückgeben. Dadurch wird die Verbindung zwischen Quelle und Senke unterbricht.

Achten Sie darauf, bei der Behandlung von Ereignissen Verweis Zyklen zu vermeiden.

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)
