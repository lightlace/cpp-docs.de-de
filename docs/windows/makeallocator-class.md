---
title: MakeAllocator-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: 805f0c09b0490d8cec1a0be96dcb1fc99a051371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476218"
---
# <a name="makeallocator-class"></a>MakeAllocator-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typname.

*hasWeakReferenceSupport*<br/>
**"true"** zum Zuweisen von Arbeitsspeicher für ein Objekt, das schwache Verweise; unterstützt. **"false"** zum Zuweisen von Arbeitsspeicher für ein Objekt, das schwache Verweise nicht unterstützt.

## <a name="remarks"></a>Hinweise

Belegt Speicher für eine aktivierbare Klasse, mit oder ohne Unterstützung von schwachen Verweis.

Überschreiben der `MakeAllocator` Klasse, um eine benutzerdefinierte Zuordnung Speichermodell zu implementieren.

`MakeAllocator` wird normalerweise verwendet, um Speicherverluste zu verhindern, wenn ein Objekt während der Erstellung auslöst.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                  | Beschreibung
----------------------------------------------------- | ----------------------------------------------------------------
[Makeallocator:: Makeallocator](#makeallocator)        | Initialisiert eine neue Instanz der `MakeAllocator`-Klasse.
[MakeAllocator:: ~ MakeAllocator](#tilde-makeallocator) | Hebt die Initialisierung der aktuellen Instanz von der `MakeAllocator` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                 | Beschreibung
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[Makeallocator:: Allocate](#allocate) | Weist Speicher zu und ordnet es die aktuellen `MakeAllocator` Objekt.
[Makeallocator:: Detach](#detach)     | Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](#allocate) Methode aus dem aktuellen `MakeAllocator` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`MakeAllocator`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="allocate"></a>Makeallocator:: Allocate

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg einen Zeiger auf den reservierten Speicher; andernfalls `nullptr`.

### <a name="remarks"></a>Hinweise

Weist Speicher zu und ordnet es die aktuellen `MakeAllocator` Objekt.

Die Größe des zugeordneten Speichers ist die Größe des vom aktuellen angegebenen Typs `MakeAllocator` Template-Parameter.

Ein Entwickler benötigt, um nur überschreiben die `Allocate()` zu einer anderen Zuordnung Speichermodell zu implementierende Methode.

## <a name="detach"></a>Makeallocator:: Detach

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Hinweise

Hebt die Zuordnung von belegten Arbeitsspeicher die [Allocate](#allocate) Methode aus dem aktuellen `MakeAllocator` Objekt.

Wenn Sie aufrufen `Detach()`, Sie sind verantwortlich für das Löschen des Arbeitsspeichers, die bereitgestellt werden, indem die `Allocate` Methode.

## <a name="makeallocator"></a>Makeallocator:: Makeallocator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `MakeAllocator`-Klasse.

## <a name="tilde-makeallocator"></a>MakeAllocator:: ~ MakeAllocator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen Instanz von der `MakeAllocator` Klasse.

Dieser Destruktor werden bei Bedarf auch den zugrunde liegenden belegten Speicher gelöscht.
