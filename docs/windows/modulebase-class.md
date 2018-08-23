---
title: ModuleBase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6d60e5114d189ddede87899bb55fba25a296c57
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601470"
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

|Name|Beschreibung|
|----------|-----------------|
|[ModuleBase::ModuleBase-Konstruktor](../windows/modulebase-modulebase-constructor.md)|Initialisiert eine Instanz der `Module`-Klasse.|
|[ModuleBase::~ModuleBase-Destruktor](../windows/modulebase-tilde-modulebase-destructor.md)|Hebt die Initialisierung der aktuellen Instanz von der `Module` Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ModuleBase::DecrementObjectCount-Methode](../windows/modulebase-decrementobjectcount-method.md)|Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.|
|[ModuleBase::IncrementObjectCount-Methode](../windows/modulebase-incrementobjectcount-method.md)|Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ModuleBase`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)