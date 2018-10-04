---
title: RuntimeClassFlags-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c5bfd9fc6dd87c61149722e8ef7fed79f8f017da
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788837"
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
