---
title: Event-Klasse (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 2d36b4fa3d1824f43e0cfafe55c439a6bdeccb6f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785570"
---
# <a name="event-class-wrl"></a>Event-Klasse (WRL)

Stellt ein Ereignis dar.

## <a name="syntax"></a>Syntax

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                   | Beschreibung
---------------------- | ------------------------------------------------
[Event::Event](#event) | Initialisiert eine neue Instanz der `Event`-Klasse.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                 | Beschreibung
------------------------------------ | ------------------------------------------------------------------------
[Event::operator=](#operator-assign) | Weist dem angegebenen `Event` Verweis auf das aktuelle `Event` Instanz.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HandleT`

`Event`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="event"></a>Event::Event

Initialisiert eine neue Instanz der `Event`-Klasse.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein Ereignis. In der Standardeinstellung *h* wird initialisiert `nullptr`.

## <a name="operator-assign"></a>Event::operator=

Weist dem angegebenen `Event` Verweis auf das aktuelle `Event` Instanz.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf ein `Event` Instanz.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle `Event` Instanz.
