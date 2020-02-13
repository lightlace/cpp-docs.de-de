---
title: IUMSCompletionList-Struktur
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: 02382ef4606a6e73804fcbd5ce7735ecf2f0dcc7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140049"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList-Struktur

Stellt eine UMS-Vervollständigungsliste dar. Wenn ein UMS-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist. Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann. Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IUMSCompletionList:: getunblocknotification](#getunblocknotifications)|Ruft eine Kette von `IUMSUnblockNotification`-Schnittstellen ab, die Ausführungs Kontexte darstellen, deren zugeordnete Thread Proxys seit dem letzten Aufruf dieser Methode entsperrt wurden.|

## <a name="remarks"></a>Bemerkungen

Ein Planer muss besonders sorgfältig darauf achten, welche Aktionen nach dem Verwenden dieser Schnittstelle ausgeführt werden, um Elemente aus der Vervollständigungsliste aus der Warteschlange zu entfernen. Die Elemente sollten in der Liste der ausführbaren Kontexte des Planers abgelegt werden und sind in der Regel so schnell wie möglich zugänglich. Es ist durchaus möglich, dass eines der aus der Warteschlange befindlichen Elemente den Besitz einer willkürlichen Sperre erhält. Der Planer kann keine beliebigen Funktionsaufrufe vornehmen, die zwischen dem Aufruf zum Entfernen von Elementen aus der Warteschlange und der Platzierung dieser Elemente in einer Liste blockiert werden können, auf die im Zeit Planungs Modul normalerweise zugegriffen werden kann.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IUMSCompletionList`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="getunblocknotifications"></a>IUMSCompletionList:: getunblocknotification-Methode

Ruft eine Kette von `IUMSUnblockNotification`-Schnittstellen ab, die Ausführungs Kontexte darstellen, deren zugeordnete Thread Proxys seit dem letzten Aufruf dieser Methode entsperrt wurden.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Kette von `IUMSUnblockNotification` Schnittstellen.

### <a name="remarks"></a>Bemerkungen

Die zurückgegebenen Benachrichtigungen sind ungültig, sobald die Ausführungs Kontexte neu geplant wurden.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IUMSScheduler-Struktur](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification-Struktur](iumsunblocknotification-structure.md)
