---
title: FactoryCacheFlags-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 8cf4af2ac0b4557fc6b175b84c47f83dd8a6e4ba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037444"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags-Enumeration

Bestimmt, ob die Factory-Objekte zwischengespeichert werden.

## <a name="syntax"></a>Syntax

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung die Cacherichtlinie Factory angegeben ist, als die [ModuleType](moduletype-enumeration.md) Template-Parameter, die bei der Erstellung einer [Modul](module-class.md) Objekt. Um diese Richtlinie überschreiben, geben Sie einen **FactoryCacheFlags** Wert, wenn Sie ein Factoryobjekt zu erstellen.

|||
|-|-|
|`FactoryCacheDefault`|Die Cachingrichtlinie für die `Module` Objekt verwendet wird.|
|`FactoryCacheEnabled`|Aktiviert die Factory Zwischenspeicherung, unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|
|`FactoryCacheDisabled`|Deaktiviert die Factory im Cache unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)