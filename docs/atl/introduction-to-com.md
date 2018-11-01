---
title: Einführung in COM
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 7a200a964e0cba09878929e4362385e5badd10c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492855"
---
# <a name="introduction-to-com"></a>Einführung in COM

COM ist die grundlegenden "Objektmodell", welche ActiveX-Steuerelemente und OLE erstellt werden. COM ermöglicht ein Objekt, dessen Funktionalität mit anderen Komponenten und hostanwendungen verfügbar zu machen. Sie definiert sowohl wie das Objekt selbst verfügbar macht und wie dieses Offenlegen über Prozesse und über Netzwerke hinweg funktioniert. COM definiert auch die Lebensdauer des Objekts.

Für COM grundlegende diese Konzepte sind:

- [Schnittstellen](../atl/interfaces-atl.md) – der Mechanismus, durch die ein Objekt seine Funktionalität verfügbar macht.

- [IUnknown](../atl/iunknown.md) – die grundlegende Schnittstelle, die auf dem alle anderen basieren. Außerdem implementiert die verweiszählung und Abfragen von Mechanismen, die ausgeführt wird, über COM-Schnittstelle

- [Verweiszählung](../atl/reference-counting.md) – die Technik, mit dem ein Objekt (oder streng genommen eine Schnittstelle) entscheidet, wenn es nicht mehr verwendet wird und aus diesem Grund können sich selbst zu entfernen.

- [QueryInterface](../atl/queryinterface.md) – die Methode verwendet, um ein Objekt für die jeweilige Schnittstelle abzufragen.

- [Marshalling](../atl/marshaling.md) – der Mechanismus, der Objekte in der gesamten Threads, Prozesse und Netzwerkgrenzen, sodass Standortunabhängigkeit verwendet werden kann.

- [Aggregation](../atl/aggregation.md) – eine Möglichkeit für die ein Objekt, kann von einer anderen verwenden.

## <a name="see-also"></a>Siehe auch

[Einführung in COM und ATL](../atl/introduction-to-com-and-atl.md)<br/>
[Das Component Object Model](/windows/desktop/com/the-component-object-model)

