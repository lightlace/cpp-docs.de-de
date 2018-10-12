---
title: SyncLockT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66aa9c3a8ab0f5ae9fb5219b090ec5c9e3755203
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162099"
---
# <a name="synclockt-class"></a>SyncLockT-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Parameter

*SyncTraits*<br/>
Der Typ, der Besitz einer Ressource übernehmen kann.

## <a name="remarks"></a>Hinweise

Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.

Die `SyncLockT` Klasse wird verwendet, z. B. zum Implementieren der [SRWLock](../windows/srwlock-class.md) Klasse.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                      | Beschreibung
----------------------------------------- | ----------------------------------------------------
[Synclockt:: Synclockt](#synclockt)        | Initialisiert eine neue Instanz der `SyncLockT`-Klasse.
[SyncLockT:: ~ SyncLockT](#tilde-synclockt) | Hebt die Initialisierung einer Instanz von der `SyncLockT` Klasse.

### <a name="protected-constructors"></a>Geschützte Konstruktoren

Name                               | Beschreibung
---------------------------------- | ----------------------------------------------------
[Synclockt:: Synclockt](#synclockt) | Initialisiert eine neue Instanz der `SyncLockT`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                             | Beschreibung
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[Synclockt:: IsLocked](#islocked) | Gibt an, ob die aktuelle `SyncLockT` Objekt besitzt eine Ressource, d. h. die `SyncLockT` Objekt *gesperrt*.
[Synclockt:: Unlock](#unlock)     | Gibt die Steuerung der Ressource frei, die von der aktuellen frei `SyncLockT` Objekt, sofern vorhanden.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                      | Beschreibung
------------------------- | -------------------------------------------------------------------
[Synclockt:: Sync_](#sync) | Enthält die zugrunde liegende Ressource dargestellt wird, durch die `SyncLockT` Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SyncLockT`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="tilde-synclockt"></a>SyncLockT:: ~ SyncLockT

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung einer Instanz von der `SyncLockT` Klasse.

Dieser Destruktor entsperrt auch die aktuelle `SyncLockT` Instanz.

## <a name="islocked"></a>Synclockt:: IsLocked

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `SyncLockT` Objekt gesperrt ist; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Gibt an, ob die aktuelle `SyncLockT` Objekt besitzt eine Ressource, d. h. die `SyncLockT` Objekt *gesperrt*.

## <a name="sync"></a>Synclockt:: Sync_

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Hinweise

Enthält die zugrunde liegende Ressource dargestellt wird, durch die `SyncLockT` Klasse.

## <a name="synclockt"></a>Synclockt:: Synclockt

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Rvalue-Verweis auf einen anderen `SyncLockT` Objekt.

*sync*<br/>
Ein Verweis auf einen anderen `SyncLockWithStatusT` Objekt.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `SyncLockT`-Klasse.

Der erste Konstruktor initialisiert die aktuelle `SyncLockT` Objekt von einem anderen `SyncLockT` vom Parameter angegebenen Objekts *andere*, und erklärt klicken Sie dann die andere `SyncLockT` Objekt. Der zweite Konstruktor ist `protected`, und initialisiert die aktuelle `SyncLockT` Objekt, das einen ungültigen Status.

## <a name="unlock"></a>Synclockt:: Unlock

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void Unlock();
```

### <a name="remarks"></a>Hinweise

Gibt die Steuerung der Ressource frei, die von der aktuellen frei `SyncLockT` Objekt, sofern vorhanden.
