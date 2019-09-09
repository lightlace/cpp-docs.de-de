---
title: Einführung in COM
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: e29f761e0380357bc999af82cc4bde8bfbaf4d6e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492360"
---
# <a name="introduction-to-com"></a>Einführung in COM

COM ist das grundlegende "Objektmodell", für das ActiveX-Steuerelemente und OLE erstellt werden. COM ermöglicht einem Objekt, seine Funktionalität für andere Komponenten und für das Hosten von Anwendungen verfügbar zu machen. Es definiert sowohl, wie das Objekt sich selbst verfügbar macht, als auch, wie diese Offenlegung zwischen Prozessen und Netzwerk übergreifend funktioniert. COM definiert auch den Lebenszyklus des Objekts.

Grundlegend für com sind folgende Konzepte:

- [Schnittstellen](../atl/interfaces-atl.md) – der Mechanismus, über den ein Objekt seine Funktionalität verfügbar macht.

- [IUnknown](../atl/iunknown.md) – die grundlegende Schnittstelle, auf der alle anderen basieren. Es implementiert die Verweis Zählung und die Schnittstellen Abfrage Mechanismen, die über com ausgeführt werden.

- [Verweis Zählung](../atl/reference-counting.md) – die Methode, mit der ein Objekt (oder, streng, eine Schnittstelle) entscheidet, wenn es nicht mehr verwendet wird und daher frei entfernt werden kann.

- [QueryInterface](../atl/queryinterface.md) – die Methode, mit der ein Objekt für eine bestimmte Schnittstelle abgefragt wird.

- [Marshalling – der](../atl/marshaling.md) Mechanismus, mit dem Objekte über Thread-, Prozess-und Netzwerk Grenzen hinweg verwendet werden können, sodass Standortunabhängigkeit möglich ist.

- [Aggregation](../atl/aggregation.md) – eine Methode, mit der ein Objekt ein anderes verwenden kann.

## <a name="see-also"></a>Siehe auch

[Einführung in COM und ATL](../atl/introduction-to-com-and-atl.md)<br/>
[Das Component Object Model](/windows/win32/com/the-component-object-model)
