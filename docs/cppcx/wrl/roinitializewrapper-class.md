---
title: RoInitializeWrapper-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b43d5bb2f553d298584ab2ae497c22637d3beb0d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784234"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper-Klasse

Initialisiert die Windows-Runtime.

## <a name="syntax"></a>Syntax

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Hinweise

`RoInitializeWrapper` wird aus Gründen der benutzerfreundlichkeit, die die Windows-Runtime initialisiert und gibt ein HRESULT zurück, der angibt, ob der Vorgang erfolgreich war. Da der Destruktor einer Klasse aufruft `::Windows::Foundation::Uninitialize`, Instanzen von `RoInitializeWrapper` müssen im globalen oder der obersten Ebene Gültigkeitsbereich deklariert werden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                                    | Beschreibung
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper::RoInitializeWrapper](#roinitializewrapper)        | Initialisiert eine neue Instanz der `RoInitializeWrapper`-Klasse.
[RoInitializeWrapper::~RoInitializeWrapper](#tilde-roinitializewrapper) | Zerstört die aktuelle Instanz von der `RoInitializeWrapper` Klasse.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                       | Beschreibung
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper::HRESULT()](#hresult) | Ruft den HRESULT-Wert, erzeugt die `RoInitializeWrapper` Konstruktor.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RoInitializeWrapper`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="hresult"></a>RoInitializeWrapper::HRESULT()

Ruft der HRESULT-Wert, der von der letzten erzeugten `RoInitializeWrapper` Konstruktor.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapper"></a>RoInitializeWrapper::RoInitializeWrapper

Initialisiert eine neue Instanz der `RoInitializeWrapper`-Klasse.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Parameter

*flags*<br/>
Einer der RO_INIT_TYPE Enumerationen, die angibt, die von der Windows-Runtime-Unterstützung.

### <a name="remarks"></a>Hinweise

Die `RoInitializeWrapper` Klasse ruft `Windows::Foundation::Initialize(flags)`.

## <a name="tilde-roinitializewrapper"></a>RoInitializeWrapper::~RoInitializeWrapper

Hebt die Initialisierung der Windows-Runtime.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Hinweise

Die `RoInitializeWrapper` Klasse ruft `Windows::Foundation::Uninitialize()`.
