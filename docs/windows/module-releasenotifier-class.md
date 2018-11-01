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
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475906"
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
[Module:: releasenotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Hebt die Initialisierung der aktuellen Instanz von der `Module::ReleaseNotifier` Klasse.
[Module::ReleaseNotifier::ReleaseNotifier](#releasenotifier-releasenotifier)        | Initialisiert eine neue Instanz der `Module::ReleaseNotifier`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module:: releasenotifier:: Invoke](#releasenotifier-invoke)   | Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul veröffentlicht wird.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Löscht die aktuelle `Module::ReleaseNotifier` Objekt, wenn das Objekt, mit dem Parameter erstellt wurde **"true"**.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ReleaseNotifier`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module:: releasenotifier:: ~ ReleaseNotifier

Hebt die Initialisierung der aktuellen Instanz von der `Module::ReleaseNotifier` Klasse.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module:: releasenotifier:: Invoke

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
