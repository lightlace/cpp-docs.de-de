---
title: Module::GenericReleaseNotifier-Klasse
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: 318415c9726426cbd60c205759a6ff8572cc555e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325051"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier-Klasse

Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler ist durch ein Lambda, Funktionselement oder Zeiger auf Funktion angegeben.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Datenmembers, der den Speicherort des ereignishandlers enthält.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                                                                     | Beschreibung
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module::GenericReleaseNotifier::GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | Initialisiert eine neue Instanz der `Module::GenericReleaseNotifier`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                                     | Beschreibung
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier::Invoke](#genericreleasenotifier-invoke) | Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::GenericReleaseNotifier` Objekt.

### <a name="protected-data-members"></a>Geschützte Datenmember

Name                                                                          | Beschreibung
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier::callback_](#genericreleasenotifier-callback) | Enthält den Lambda, Funktionselement oder Zeiger auf Funktion zugeordnete Ereignishandler die aktuelle `Module::GenericReleaseNotifier` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="genericreleasenotifier-callback"></a>Module::GenericReleaseNotifier::callback_

Enthält den Lambda, Funktionselement oder Zeiger auf Funktion zugeordnete Ereignishandler die aktuelle `Module::GenericReleaseNotifier` Objekt.

```cpp
T callback_;
```

## <a name="genericreleasenotifier-genericreleasenotifier"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier

Initialisiert eine neue Instanz der `Module::GenericReleaseNotifier`-Klasse.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parameter

*callback*<br/>
Ein Lambda, Funktionselement oder Zeiger auf Funktion-Ereignishandler, der mit dem Klammernoperator-Funktion aufgerufen werden kann (`()`).

*release*<br/>
Geben Sie `true` aktivieren aufrufen, die zugrunde liegende [Modul:: ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) Methode geben Sie andernfalls `false`.

## <a name="genericreleasenotifier-invoke"></a>Module::GenericReleaseNotifier::Invoke

Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::GenericReleaseNotifier` Objekt.

```cpp
void Invoke();
```
