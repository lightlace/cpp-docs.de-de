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
ms.openlocfilehash: ec3c38ee609dfa7aec8d688269f1183d307be5b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438206"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList-Struktur

Stellt eine UMS-Vervollständigungsliste dar. Wenn ein UMS-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist. Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann. Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.

## <a name="syntax"></a>Syntax

```
struct IUMSCompletionList;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Ruft ab eine Kette von `IUMSUnblockNotification` Schnittstellen, darstellen, Ausführungskontexte, deren zugeordnete Threadproxys seit der letzten Ausführung dieser Methode aufgerufen wurde.|

## <a name="remarks"></a>Hinweise

Ein Planer muss besonders vorsichtig, welche Aktionen ausgeführt werden, nachdem diese Schnittstelle zum Entfernen von Elementen aus der Liste sein. Die Elemente des Planers Liste ausführbarer Kontexte platziert werden soll, und es so bald wie möglich in der Regel zugegriffen werden. Es ist durchaus möglich, dass eines der Elemente aus der Warteschlange entfernt den Besitz einer beliebigen Sperre zugewiesen wurde. Der Scheduler kann es sich um keine beliebige Funktion-Aufrufe ausführen, die Blockierung verursachen können, zwischen dem Elemente aus der Warteschlange entfernt und die Platzierung dieser Elemente in einer Liste, die in der Regel innerhalb des Planers aus zugegriffen werden kann.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IUMSCompletionList`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="getunblocknotifications"></a>  IUMSCompletionList:: GetUnblockNotifications-Methode

Ruft ab eine Kette von `IUMSUnblockNotification` Schnittstellen, darstellen, Ausführungskontexte, deren zugeordnete Threadproxys seit der letzten Ausführung dieser Methode aufgerufen wurde.

```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Kette von `IUMSUnblockNotification` Schnittstellen.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Benachrichtigungen sind ungültig, nachdem die Ausführungskontexte geplant werden.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IUMSScheduler-Struktur](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification-Struktur](iumsunblocknotification-structure.md)
