---
title: Marshalling
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: a6129ba96cf3ac11339a8ab953e0838127f8fb3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569792"
---
# <a name="marshaling"></a>Marshalling

Das Verfahren der COM-Marshalling kann Schnittstellen verfügbar gemacht werden, von einem Objekt in einem Prozess in einem anderen Prozess verwendet werden. Marshalling COM stellt Code bereit (oder verwendet den von der Implementierung der Schnittstelle bereitgestellten Code) Parameter einer Methode in einem Format packen, die zwischen Prozessen (sowie über das Netzwerk für laufende Prozesse auf anderen Computern) verschoben werden können und Entpacken Sie diese Parameter am anderen Ende. Ebenso muss COM dieselben Schritte bei der Rückgabe aus dem Aufruf ausführen.

> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle zur Verfügung gestellt, von einem Objekt im selben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Marshalling von Details](/windows/desktop/com/marshaling-details)

