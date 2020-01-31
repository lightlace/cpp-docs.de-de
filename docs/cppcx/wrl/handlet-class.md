---
title: HandleT-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: f66fbe23c305be15e09928242175dfa7ce8c141b
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821817"
---
# <a name="handlet-class"></a>HandleT-Klasse

Stellt ein Handle für ein-Objekt dar.

## <a name="syntax"></a>Syntax

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Parameters

*HandleTraits*<br/>
Eine Instanz der [Lenker](handletraits-structure.md) Struktur, die allgemeine Merkmale eines Handles definiert.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

-Name     | Beschreibung
-------- | -----------------------------
`Traits` | Ein Synonym für `HandleTraits`.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

-Name                                | Beschreibung
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | Initialisiert eine neue Instanz der `HandleT` -Klasse.
[HandleT::~HandleT](#tilde-handlet) | Deinitialisiert eine Instanz der `HandleT`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

-Name                         | Beschreibung
---------------------------- | ----------------------------------------------------------------------
[Handlet:: Attach](#attach)   | Ordnet das angegebene Handle dem aktuellen `HandleT`-Objekt zu.
[Handlet:: Close](#close)     | Schließt das aktuelle `HandleT`-Objekt.
[Handlet::D Etach](#detach)   | Hebt die Zuordnung des aktuellen `HandleT` Objekts zum zugrunde liegenden Handle auf.
[HandleT::Get](#get)         | Ruft den Wert des zugrunde liegenden Handles ab.
[HandleT::IsValid](#isvalid) | Gibt an, ob das aktuelle `HandleT`-Objekt ein Handle darstellt.

### <a name="protected-methods"></a>Geschützte Methoden

-Name                                     | Beschreibung
---------------------------------------- | ------------------------------------
[HandleT::InternalClose](#internalclose) | Schließt das aktuelle `HandleT`-Objekt.

### <a name="public-operators"></a>Öffentliche Operatoren

-Name                                   | Beschreibung
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator=](#operator-assign) | Verschiebt den Wert des angegebenen `HandleT` Objekts in das aktuelle `HandleT`-Objekt.

### <a name="protected-data-members"></a>Geschützte Datenelemente

-Name                        | Beschreibung
--------------------------- | ----------------------------------------------------------------
[Handlet:: handle_](#handle) | Enthält das Handle, das durch das `HandleT`-Objekt dargestellt wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HandleT`

## <a name="requirements"></a>-Anforderungen

**Header:** corewrappers. h

**Namespace:** Microsoft:: WRL:: Wrapper

## <a name="tilde-handlet"></a>Handlet:: ~ handlet

Deinitialisiert eine Instanz der `HandleT`-Klasse.

```cpp
~HandleT();
```

## <a name="attach"></a>Handlet:: Attach

Ordnet das angegebene Handle dem aktuellen `HandleT`-Objekt zu.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parameters

*h*<br/>
Ein-handle.

## <a name="close"></a>Handlet:: Close

Schließt das aktuelle `HandleT`-Objekt.

```cpp
void Close();
```

### <a name="remarks"></a>Hinweise

Das Handle, das der aktuellen `HandleT` zugrunde liegt, wird geschlossen, und der `HandleT` wird auf den ungültigen Zustand festgelegt.

Wenn das Handle nicht ordnungsgemäß geschlossen wird, wird im aufrufenden Thread eine Ausnahme ausgelöst.

## <a name="detach"></a>Handlet::D Etach

Hebt die Zuordnung des aktuellen `HandleT` Objekts zum zugrunde liegenden Handle auf.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Rückgabewert

Das zugrunde liegende Handle.

### <a name="remarks"></a>Hinweise

Wenn dieser Vorgang abgeschlossen ist, wird der aktuelle `HandleT` auf den ungültigen Zustand festgelegt.

## <a name="get"></a>Handlet:: Get

Ruft den Wert des zugrunde liegenden Handles ab.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Rückgabewert

Ein-handle.

## <a name="handle"></a>Handlet:: handle_

Enthält das Handle, das durch das `HandleT`-Objekt dargestellt wird.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>Handlet:: handlet

Initialisiert eine neue Instanz der `HandleT` -Klasse.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameters

*h*<br/>
Ein-handle.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein `HandleT` Objekt, das kein gültiges Handle für ein-Objekt ist. Der zweite Konstruktor erstellt ein neues `HandleT`-Objekt aus dem-Parameter *h*.

## <a name="internalclose"></a>HandleT::InternalClose

Schließt das aktuelle `HandleT`-Objekt.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn die aktuelle `HandleT` erfolgreich geschlossen wurde. andernfalls **false**.

### <a name="remarks"></a>Hinweise

`InternalClose()` ist `protected`.

## <a name="isvalid"></a>HandleT::IsValid

Gibt an, ob das aktuelle `HandleT`-Objekt ein Handle darstellt.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn die `HandleT` ein Handle darstellt. andernfalls **false**.

## <a name="operator-assign"></a>Handlet:: Operator =

Verschiebt den Wert des angegebenen `HandleT` Objekts in das aktuelle `HandleT`-Objekt.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameters

*h*<br/>
Ein rvalue-Verweis auf ein handle.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle `HandleT`-Objekt.

### <a name="remarks"></a>Hinweise

Durch diesen Vorgang wird das durch den Parameter *h*angegebene `HandleT` Objekt ungültig.
