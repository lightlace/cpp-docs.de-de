---
title: Duale Schnittstellen und Ereignisse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99dc173f3dde8ea81f6dc11d02298cd94673f999
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354066"
---
# <a name="dual-interfaces-and-events"></a>Duale Schnittstellen und Ereignisse
Es ist, zwar möglich, eine Ereignisschnittstelle als Dual entwerfen stehen eine Reihe von guten Entwurfsgründen nicht zu tun. Die grundlegende Ursache ist, dass die Quelle des Ereignisses nur, das Ereignis Vtable oder über ausgelöst werden `Invoke`, aber nicht beides. Wenn die Ereignisquelle des Ereignisses als eine direkte Vtable-Methodenaufruf Auslösung, der `IDispatch` Methoden werden nie verwendet werden, und es ist klar, dass die Schnittstelle sollte eine reine Vtable-Schnittstelle wurde. Wenn die Ereignisquelle des Ereignisses als Aufruf Auslösung `Invoke`werden nie die Vtable-Methoden verwendet werden, und es ist klar, dass die Schnittstelle einer Dispinterface hätten verwendet werden soll. Wenn Sie Ihre Ereignisschnittstellen als duale Schnittstellen definieren, müssen Sie erfordern werden Clients, die Teil einer Schnittstelle zu implementieren, die nie verwendet wird.  
  
> [!NOTE]
>  Dieses Argument gilt im Allgemeinen nicht für duale Schnittstellen. Aus Implementierungssicht sind die Entwurfssicht schnelle, bequeme und gut unterstützte Möglichkeit zum Implementieren von Schnittstellen, die in einer breiten Palette von Clients zugegriffen werden kann.  
  
 Es gibt weitere Gründe für die duale Ereignisschnittstellen; weder Internet Explorer als auch Visual Basic unterstützt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

