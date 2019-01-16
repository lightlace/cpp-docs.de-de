---
title: Module::ReleaseNotifier-Klasse
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: 5fc1b8965bf8bf2f86dd30f2195fa825f85f6d7e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336087"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier-Klasse

Ruft einen Ereignishandler an, wenn das letzte Objekt in einem Modul veröffentlicht wird.

## <a name="syntax"></a>Syntax

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                                                | Beschreibung
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module::ReleaseNotifier::~ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Hebt die Initialisierung der aktuellen Instanz von der `Module::ReleaseNotifier` Klasse.
[Module::ReleaseNotifier::ReleaseNotifier](#releasenotifier-releasenotifier)        | Initialisiert eine neue Instanz der `Module::ReleaseNotifier`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module::ReleaseNotifier::Invoke](#releasenotifier-invoke)   | Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul veröffentlicht wird.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Löscht die aktuelle `Module::ReleaseNotifier` Objekt, wenn das Objekt, mit dem Parameter erstellt wurde **"true"**.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ReleaseNotifier`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module::ReleaseNotifier::~ReleaseNotifier

Hebt die Initialisierung der aktuellen Instanz von der `Module::ReleaseNotifier` Klasse.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module::ReleaseNotifier::Invoke

Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul veröffentlicht wird.

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module::ReleaseNotifier::Release

Löscht die aktuelle `Module::ReleaseNotifier` Objekt, wenn das Objekt, mit dem Parameter erstellt wurde **"true"**.

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module::ReleaseNotifier::ReleaseNotifier

Initialisiert eine neue Instanz der `Module::ReleaseNotifier`-Klasse.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parameter

*release*<br/>
`true` So löschen Sie diese Instanz bei der `Release` Methode wird aufgerufen. `false` diese Instanz nicht gelöscht.
