---
title: Module::MethodReleaseNotifier-Klasse
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: 41b7cfb2601cd2023e895dbcf1a56e85fe65b35d
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336159"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier-Klasse

Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler wird von einem Objekt und seine Member Zeiger-zu-Methode angegeben.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Objekts, dessen Memberfunktion der Ereignishandler ist.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                                                                 | Beschreibung
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module::MethodReleaseNotifier::MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | Initialisiert eine neue Instanz der `Module::MethodReleaseNotifier`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                                   | Beschreibung
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::Invoke](#methodreleasenotifier-invoke) | Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::MethodReleaseNotifier` Objekt.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                                                                    | Beschreibung
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::method_](#methodreleasenotifier-method) | Enthält einen Zeiger auf den Ereignishandler für das aktuelle `Module::MethodReleaseNotifier` Objekt.
[Module::MethodReleaseNotifier::object_](#methodreleasenotifier-object) | Enthält einen Zeiger auf das Objekt, dessen Memberfunktion der Ereignishandler für das aktuelle ist `Module::MethodReleaseNotifier` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="methodreleasenotifier-invoke"></a>Module::MethodReleaseNotifier::Invoke

Ruft den Ereignishandler verknüpft ist, mit dem aktuellen `Module::MethodReleaseNotifier` Objekt.

```cpp
void Invoke();
```

## <a name="methodreleasenotifier-method"></a>Module::MethodReleaseNotifier::method_

Enthält einen Zeiger auf den Ereignishandler für das aktuelle `Module::MethodReleaseNotifier` Objekt.

```cpp
void (T::* method_)();
```

## <a name="methodreleasenotifier-methodreleasenotifier"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier

Initialisiert eine neue Instanz der `Module::MethodReleaseNotifier`-Klasse.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>Parameter

*object*<br/>
Ein Objekt, dessen Memberfunktion ein Ereignishandler ist.

*method*<br/>
Die Member-Funktion des Parameters *Objekt* , den Ereignishandler.

*release*<br/>
Geben Sie `true` aktivieren aufrufen, die zugrunde liegende [Modul:: ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) Methode geben Sie andernfalls `false`.

## <a name="methodreleasenotifier-object"></a>Module::MethodReleaseNotifier::object_

Enthält einen Zeiger auf das Objekt, dessen Memberfunktion der Ereignishandler für das aktuelle ist `Module::MethodReleaseNotifier` Objekt.

```cpp
T* object_;
```
