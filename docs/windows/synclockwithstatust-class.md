---
title: SyncLockWithStatusT-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: a3c5c4306dd039a792fe0fd1e57f04d37cc67731
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663865"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parameter

*SyncTraits*<br/>
Ein Typ, der exklusiven ausführen kann oder den gemeinsamen Besitz einer Ressource.

## <a name="remarks"></a>Hinweise

Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.

Die `SyncLockWithStatusT` Klasse wird zum Implementieren der [Mutex](../windows/mutex-class1.md) und [Semaphor](../windows/semaphore-class.md) Klassen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                             | Beschreibung
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust:: Synclockwithstatust](#synclockwithstatust) | Initialisiert eine neue Instanz der `SyncLockWithStatusT`-Klasse.

### <a name="protected-constructors"></a>Geschützte Konstruktoren

Name                                                             | Beschreibung
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust:: Synclockwithstatust](#synclockwithstatust) | Initialisiert eine neue Instanz der `SyncLockWithStatusT`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                         | Beschreibung
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[Synclockwithstatust:: GetStatus](#getstatus) | Ruft den Wartestatus "des aktuellen `SyncLockWithStatusT` Objekt.
[Synclockwithstatust:: IsLocked](#islocked)   | Gibt an, ob die aktuelle `SyncLockWithStatusT` Objekt besitzt eine Ressource, d. h. die `SyncLockWithStatusT` Objekt *gesperrt*.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                                    | Beschreibung
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[Synclockwithstatust:: Status_](#status) | Das Ergebnis der zugrunde liegenden Wartevorgang enthält, nachdem ein Vorgang für ein Objekt abhängig von der aktuellen `SyncLockWithStatusT` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="getstatus"></a>Synclockwithstatust:: GetStatus

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Rückgabewert

Das Ergebnis eines Vorgangs warten auf das Objekt, das basierend auf den `SyncLockWithStatusT` Klasse, z. B. eine [Mutex](../windows/mutex-class1.md) oder [Semaphor](../windows/semaphore-class.md). 0 (null) gibt an, dass es sich bei der "Wait"-Vorgang auf den signalisierten Zustand zurückgegeben; Andernfalls ist einen anderen Status aufgetreten, z. B. Timeoutwert verstrichen.

### <a name="remarks"></a>Hinweise

Ruft den Wartestatus "des aktuellen `SyncLockWithStatusT` Objekt.

Die GetStatus()-Funktion ruft den Wert des zugrunde liegenden [Status_](#status) -Datenmember. Bei der ein Objekt auf Grundlage der `SyncLockWithStatusT` Klasse führt einen Vorgang, der das Objekt zuerst wartet darauf, dass das Objekt verfügbar sind. Das Ergebnis des Wartevorgangs befindet sich in der `status_` -Datenmember. Mögliche Werte für die `status_` Datenmember sind die Rückgabewerte des Wartevorgangs. Weitere Informationen finden Sie auf die Rückgabewerte von der `WaitForSingleObjectEx()` -Funktion in der MSDN Library.

## <a name="islocked"></a>Synclockwithstatust:: IsLocked

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Hinweise

Gibt an, ob die aktuelle `SyncLockWithStatusT` Objekt besitzt eine Ressource, d. h. die `SyncLockWithStatusT` Objekt *gesperrt*.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `SyncLockWithStatusT` Objekt gesperrt ist; andernfalls **"false"**.

## <a name="status"></a>Synclockwithstatust:: Status_

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Hinweise

Das Ergebnis der zugrunde liegenden Wartevorgang enthält, nachdem ein Vorgang für ein Objekt abhängig von der aktuellen `SyncLockWithStatusT` Objekt.

## <a name="synclockwithstatust"></a>Synclockwithstatust:: Synclockwithstatust

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Rvalue-Verweis auf einen anderen `SyncLockWithStatusT` Objekt.

*sync*<br/>
Ein Verweis auf einen anderen `SyncLockWithStatusT` Objekt.

*Status*<br/>
Der Wert des der [Status_](#status) Datenmember der *andere* Parameter oder die *Sync* Parameter.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `SyncLockWithStatusT`-Klasse.

Der erste Konstruktor initialisiert die aktuelle `SyncLockWithStatusT` Objekt von einem anderen `SyncLockWithStatusT` vom-Parameter angegebenen *andere*, und erklärt klicken Sie dann die andere `SyncLockWithStatusT` Objekt. Der zweite Konstruktor ist `protected`, und initialisiert die aktuelle `SyncLockWithStatusT` Objekt, das einen ungültigen Status.
