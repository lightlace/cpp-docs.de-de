---
title: ModuleBase-Klasse
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 254796c03d25a77da22c48881c086a41ffbfeb82
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335986"
---
# <a name="modulebase-class"></a>ModuleBase-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Hinweise

Stellt die Basisklasse der [Modul](module-class.md) Klassen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                         | Beschreibung
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | Initialisiert eine Instanz der `Module`-Klasse.
[ModuleBase::~ModuleBase](#tilde-modulebase) | Hebt die Initialisierung der aktuellen Instanz von der `Module` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                      | Beschreibung
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.
[ModuleBase::IncrementObjectCount](#incrementobjectcount) | Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ModuleBase`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-modulebase"></a>ModuleBase::~ModuleBase

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen Instanz von der `ModuleBase` Klasse.

## <a name="decrementobjectcount"></a>ModuleBase::DecrementObjectCount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor der dekrementvorgang werden soll.

### <a name="remarks"></a>Hinweise

Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.

## <a name="incrementobjectcount"></a>ModuleBase::IncrementObjectCount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor dem Inkrementieren negativ werden soll.

### <a name="remarks"></a>Hinweise

Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

## <a name="modulebase"></a>ModuleBase::ModuleBase

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Hinweise

Initialisiert eine Instanz der `Module`-Klasse.
