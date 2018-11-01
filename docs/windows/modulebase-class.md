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
ms.openlocfilehash: 4a65b7335626cc36a4eecbe61465778889a9e7e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502127"
---
# <a name="modulebase-class"></a>ModuleBase-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Hinweise

Stellt die Basisklasse der [Modul](../windows/module-class.md) Klassen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                         | Beschreibung
-------------------------------------------- | ---------------------------------------------------------
[Modulebase:: Modulebase](#modulebase)        | Initialisiert eine Instanz der `Module`-Klasse.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Hebt die Initialisierung der aktuellen Instanz von der `Module` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                      | Beschreibung
--------------------------------------------------------- | -------------------------------------------------------------------------
[Modulebase:: Decrementobjectcount](#decrementobjectcount) | Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.
[Modulebase:: Incrementobjectcount](#incrementobjectcount) | Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ModuleBase`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-modulebase"></a>ModuleBase:: ~ ModuleBase

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen Instanz von der `ModuleBase` Klasse.

## <a name="decrementobjectcount"></a>Modulebase:: Decrementobjectcount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor der dekrementvorgang werden soll.

### <a name="remarks"></a>Hinweise

Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.

## <a name="incrementobjectcount"></a>Modulebase:: Incrementobjectcount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor dem Inkrementieren negativ werden soll.

### <a name="remarks"></a>Hinweise

Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

## <a name="modulebase"></a>Modulebase:: Modulebase

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Hinweise

Initialisiert eine Instanz der `Module`-Klasse.
