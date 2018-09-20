---
title: SyncLockWithStatusT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69676651c77175b55f4363b525a3ca3acb9be46d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437455"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename SyncTraits
>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parameter

*SyncTraits*<br/>
Ein Typ, der exklusiven ausführen kann oder den gemeinsamen Besitz einer Ressource.

## <a name="remarks"></a>Hinweise

Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.

Die **SyncLockWithStatusT** Klasse wird zum Implementieren der [Mutex](../windows/mutex-class1.md) und [Semaphor](../windows/semaphore-class.md) Klassen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der dem **SyncLockWithStatusT** Klasse.|

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[SyncLockWithStatusT::SyncLockWithStatusT-Konstruktor](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialisiert eine neue Instanz der dem **SyncLockWithStatusT** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SyncLockWithStatusT::GetStatus-Methode](../windows/synclockwithstatust-getstatus-method.md)|Ruft den Wartestatus "des aktuellen **SyncLockWithStatusT** Objekt.|
|[SyncLockWithStatusT::IsLocked-Methode](../windows/synclockwithstatust-islocked-method.md)|Gibt an, ob die aktuelle **SyncLockWithStatusT** Objekt besitzt eine Ressource, d. h. die **SyncLockWithStatusT** Objekt *gesperrt*.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[SyncLockWithStatusT::status_-Datenmember](../windows/synclockwithstatust-status-data-member.md)|Das Ergebnis der zugrunde liegenden Wartevorgang enthält, nachdem ein Vorgang für ein Objekt abhängig von der aktuellen **SyncLockWithStatusT** Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)