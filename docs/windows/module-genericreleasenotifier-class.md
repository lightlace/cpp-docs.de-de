---
title: 'Module:: genericreleasenotifier-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18aeac7767fbd4c1688b202670a812e5738ef62f
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494425"
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
[Module:: genericreleasenotifier:: Invoke](#genericreleasenotifier-invoke) | Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::GenericReleaseNotifier` Objekt.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                                                                          | Beschreibung
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

*Rückruf*  
Ein Lambda, Funktionselement oder Zeiger auf Funktion-Ereignishandler, der mit dem Klammernoperator-Funktion aufgerufen werden kann (`()`).

*release*  
Geben Sie `true` aktivieren aufrufen, die zugrunde liegende [Modul:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) Methode geben Sie andernfalls `false`.

## <a name="genericreleasenotifier-invoke"></a>Module:: genericreleasenotifier:: Invoke

Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::GenericReleaseNotifier` Objekt.

```cpp
void Invoke();
```
