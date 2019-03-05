---
title: Duale Schnittstellen und Ereignisse
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 01233edb63145d69d335349bb9dff91e6a4aca5a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292543"
---
# <a name="dual-interfaces-and-events"></a>Duale Schnittstellen und Ereignisse

Es ist, zwar möglich, eine Event-Schnittstelle als Dual entwerfen stehen eine Reihe von Gründen ein guter Entwurf, nicht zu tun. Die grundlegende Ursache ist, dass das Ereignis über die Vtable oder nur von der Quelle des Ereignisses ausgelöst werden `Invoke`, aber nicht beides. Wenn die Ereignisquelle wird, das Ereignis als eine direkte Vtable-Methodenaufruf ausgelöst, der `IDispatch` Methoden nicht verwendet wird, und es ist klar, dass die Schnittstelle sollte eine reine Vtable-Schnittstelle wurde. Wenn die Ereignisquelle als Aufruf an das Ereignis ausgelöst wird `Invoke`, die Vtable-Methoden nicht verwendet wird, und es ist klar, dass die Schnittstelle sollte eine Disp-Schnittstelle wurde. Wenn Sie Ihre Ereignisschnittstellen als duale Schnittstellen definieren, müssen Sie erfordert Clients, die Teil einer Schnittstelle zu implementieren, die nie verwendet wird.

> [!NOTE]
>  Dieses Argument gilt im Allgemeinen nicht für duale Schnittstellen. Aus Implementierungssicht sind duale Schnittstellen für eine schnelle, bequeme und gut unterstützte Möglichkeit zum Implementieren von Schnittstellen, die für eine Breite Palette von Clients zugänglich sind.

Es gibt weitere Gründe für die duale Ereignisschnittstellen zu vermeiden; weder Internet Explorer als auch Visual Basic unterstützt.

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)
