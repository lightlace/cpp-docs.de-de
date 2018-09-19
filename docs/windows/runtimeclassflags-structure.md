---
title: RuntimeClassFlags-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/07/2018
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
ms.openlocfilehash: 6c3cb141576598aa39c718316048900622c4df41
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691457"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags-Struktur

Enthält den Typ für eine Instanz von einem [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <
   unsigned int flags
>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parameter

*flags*  
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
