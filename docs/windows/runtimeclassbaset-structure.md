---
title: RuntimeClassBaseT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d137281d7f573275b216eecaea9e4f09564b9f6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206550"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   unsigned int RuntimeClassTypeT
>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parameter

*RuntimeClassTypeT*  
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.

## <a name="remarks"></a>Hinweise

Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.

## <a name="members"></a>Member

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RuntimeClassBaseT`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Referenz (Windows-Runtime-Bibliothek)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)