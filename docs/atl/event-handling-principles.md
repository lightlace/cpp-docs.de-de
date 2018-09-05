---
title: Prinzipien (ATL) für die Ereignisbehandlung | Microsoft-Dokumentation
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
ms.openlocfilehash: 9931e194236871b9d767805464928fd4e553015e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762872"
---
# <a name="event-handling-principles"></a>Ereignisbehandlungsrichtlinien

Es sind drei Schritte für alle Ereignisbehandlung. Sie müssen:

- Implementieren Sie die Schnittstelle für das Objekt an.

- Empfehlen Sie, dass das Objekt zum Empfangen von Ereignissen soll der Ereignisquelle.

- Abzumelden Sie die Ereignisquelle, wenn das Objekt nicht mehr benötigt wird, um Ereignisse zu empfangen.

Die Möglichkeit, dass Sie die Schnittstelle implementieren werden hängt von den Typ ab. Eine Ereignisschnittstelle möglich Vtable, Dual oder eine Disp-Schnittstelle. Es liegt in den Designer der Ereignisquelle, die Schnittstelle zu definieren; Es liegt an Ihnen, diese Schnittstelle implementieren.

> [!NOTE]
>  Es gibt, zwar keine aus technischen Gründen, die eine Ereignisschnittstelle dual sein kann gibt es jedoch aus verschiedenen Gründen ein guter Entwurf, um die Verwendung von duale Schnittstellen zu vermeiden. Dies ist jedoch durch die Designer/Implementierung des Ereignisses anhängig *Quelle*. Da Sie aus der Perspektive des Ereignisses arbeiten `sink`, müssen Sie die Möglichkeit zu ermöglichen, dass Sie keine Wahl haben, können jedoch eine duale Ereignisschnittstelle implementieren. Weitere Informationen zu duale Schnittstellen, finden Sie unter [duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md).

Anmelden der Ereignisquelle kann in drei Schritte unterteilt werden:

- Das Quellobjekt für Abfragen [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Rufen Sie [IConnectionPointContainer:: FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) übergeben Sie die IID der Ereignisschnittstelle, die Sie interessiert sind. Wenn der Erfolg dieser zurückgibt, die [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) Schnittstelle für ein-Objekt.

- Rufen Sie [IConnectionPoint:: Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) übergeben die `IUnknown` der Ereignissenke. Wenn der Erfolg dieser zurückgibt, eine `DWORD` Cookie, das die Verbindung darstellt.

Nachdem Sie Ihr Interesse am Empfang von Ereignissen registriert haben, werden Methoden für die Senkenereignis-Schnittstelle des Objekts gemäß der durch das Quellobjekt ausgelöste Ereignisse aufgerufen werden. Wenn Sie sich nicht mehr benötigen, die zum Empfangen von Ereignissen, können Sie das Cookie zurück an den Verbindungspunkt über übergeben [IConnectionPoint:: Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Dadurch wird die Verbindung zwischen Quelle und Senke unterbrochen.

Achten Sie darauf, dass Sie zu vermeiden Zyklen, wenn Sie Ereignisse behandeln.

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)

