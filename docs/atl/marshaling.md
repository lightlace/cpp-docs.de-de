---
title: Marshalling
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 9963e261f26daa57cb58e30ffc404b431d781bfa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492045"
---
# <a name="marshaling"></a>Marshalling

Mit der com-Technik des Marshalling können Schnittstellen, die von einem Objekt in einem Prozess verfügbar gemacht werden, in einem anderen Prozess verwendet werden. Beim Marshalling stellt com Code bereit (oder verwendet Code, der von der Schnittstellen Implementierung bereitgestellt wird), um die Parameter einer Methode in ein Format zu packen, das über Prozesse hinweg verschoben werden kann (sowie über das gesamte Netzwerk bis hin zu Prozessen, die auf anderen Computern ausgeführt werden), und um diese Parameter zu entpacken. am anderen Ende. Ebenso muss com dieselben Schritte für die Rückgabe des Aufrufes ausführen.

> [!NOTE]
>  Das Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle, die von einem Objekt bereitgestellt wird, im selben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Marshalling von Details](/windows/win32/com/marshaling-details)
