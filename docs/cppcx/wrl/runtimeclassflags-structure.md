---
title: RuntimeClassFlags-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 4cbd3f367bc57c2eedf672422a458b67b1908fc0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785113"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags-Struktur

Enthält den Typ für eine Instanz von einem [RuntimeClass](runtimeclass-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parameter

*flags*<br/>
Ein [RuntimeClassType-Enumeration](runtimeclasstype-enumeration.md) Wert.

## <a name="members"></a>Member

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|Beschreibung|
|----------|-----------------|
|[RuntimeClassFlags::value-Konstante](#value-constant)|Enthält eine [RuntimeClassType-Enumeration](runtimeclasstype-enumeration.md) Wert.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RuntimeClassFlags`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="value-constant"></a>Runtimeclassflags:: value-Konstante

Ein Feld mit einem [RuntimeClassType-Enumeration](runtimeclasstype-enumeration.md) Wert.

```cpp
static const unsigned int value = flags;
```
