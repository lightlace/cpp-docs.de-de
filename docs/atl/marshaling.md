---
title: Marshalling
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 0661a4cdde0a3a875cf27221e884f6c65b9fea55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262384"
---
# <a name="marshaling"></a>Marshalling

Das Verfahren der COM-Marshalling kann Schnittstellen verfügbar gemacht werden, von einem Objekt in einem Prozess in einem anderen Prozess verwendet werden. Marshalling COM stellt Code bereit (oder verwendet den von der Implementierung der Schnittstelle bereitgestellten Code) Parameter einer Methode in einem Format packen, die zwischen Prozessen (sowie über das Netzwerk für laufende Prozesse auf anderen Computern) verschoben werden können und Entpacken Sie diese Parameter am anderen Ende. Ebenso muss COM dieselben Schritte bei der Rückgabe aus dem Aufruf ausführen.

> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle zur Verfügung gestellt, von einem Objekt im selben Prozess wie das Objekt verwendet wird. Allerdings kann das Marshalling zwischen Threads erforderlich sein.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Marshalling von Details](/windows/desktop/com/marshaling-details)
