---
title: IUMSUnblockNotification-Struktur
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: d4fd95b1f11ed6edac26cb03e41e8b650acfafa3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139982"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification-Struktur

Stellt eine Benachrichtigung vom Ressourcen-Manager darüber dar, dass ein Threadproxy, der blockiert und eine Rückkehr zum festgelegten Planungskontext des Planers ausgelöst hatte, die Blockierung aufgehoben hat und zum Planen bereit ist. Diese Schnittstelle ist ungültig, sobald der zugeordnete Ausführungskontext des Threadproxys, der von der `GetContext`-Methode zurückgegeben wurde, neu geplant wird.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Iversunblocknotification:: GetContext](#getcontext)|Gibt die `IExecutionContext`-Schnittstelle für den dem Thread Proxy zugeordneten Ausführungs Kontext zurück, dessen Blockierung aufgehoben wurde. Nachdem diese Methode zurückgegeben wurde und der zugrunde liegende Ausführungs Kontext über einen aufzurufenden `IThreadProxy::SwitchTo`-Methode neu geplant wurde, ist diese Schnittstelle nicht mehr gültig.|
|[Iversunblocknotification:: GetNextUnblockNotification](#getnextunblocknotification)|Gibt die nächste `IUMSUnblockNotification` Schnittstelle in der Kette zurück, die von der-Methode `IUMSCompletionList::GetUnblockNotifications`zurückgegeben wird.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IUMSUnblockNotification`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="getcontext"></a>Ium sunblocknotification:: GetContext-Methode

Gibt die `IExecutionContext`-Schnittstelle für den dem Thread Proxy zugeordneten Ausführungs Kontext zurück, dessen Blockierung aufgehoben wurde. Nachdem diese Methode zurückgegeben wurde und der zugrunde liegende Ausführungs Kontext über einen aufzurufenden `IThreadProxy::SwitchTo`-Methode neu geplant wurde, ist diese Schnittstelle nicht mehr gültig.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine `IExecutionContext`-Schnittstelle für den Ausführungs Kontext eines Thread Proxys, der die Blockierung aufgehoben hat.

## <a name="getnextunblocknotification"></a>Ium sunblocknotification:: GetNextUnblockNotification-Methode

Gibt die nächste `IUMSUnblockNotification` Schnittstelle in der Kette zurück, die von der-Methode `IUMSCompletionList::GetUnblockNotifications`zurückgegeben wird.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die nächste `IUMSUnblockNotification`-Schnittstelle in der von der-Methode zurückgegebenen Kette `IUMSCompletionList::GetUnblockNotifications`.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IUMSScheduler-Struktur](iumsscheduler-structure.md)<br/>
[IUMSCompletionList-Struktur](iumscompletionlist-structure.md)
