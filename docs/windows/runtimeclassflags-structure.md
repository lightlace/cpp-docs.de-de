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
ms.openlocfilehash: 74ae72dc87d45abba04d15303ed2ec92b18f8c28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668532"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags-Struktur

Enthält den Typ für eine Instanz von einem [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parameter

*flags*<br/>
Ein [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md) Wert.

## <a name="members"></a>Member

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[RuntimeClassFlags::value-Konstante](#value-constant)|Enthält eine [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md) Wert.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RuntimeClassFlags`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="value-constant"></a>Runtimeclassflags:: value-Konstante

Ein Feld mit einem [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md) Wert.

```cpp
static const unsigned int value = flags;
```
