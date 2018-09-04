---
title: ImplementsHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bcacfb8d5cd6d15cf9ca5f9f5bb8e937119dc863
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691573"
---
# <a name="implementshelper-structure"></a>ImplementsHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename RuntimeClassFlagsT,
   typename ILst,
   bool IsDelegateToClass
>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parameter

*RuntimeClassFlagsT*  
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.

*ILst*  
Eine Liste der Schnittstellen-IDs.

*IsDelegateToClass*  
Geben Sie **"true"** Wenn die aktuelle Instanz von `Implements` ist eine Basisklasse, der die erste Schnittstellen-ID in *ILst*ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Hilft, implementieren die [implementiert](../windows/implements-structure.md) Struktur.

Diese Vorlage durchläuft eine Liste von Schnittstellen und fügt sie hinzu, als Basisklassen, sowie Informationen zum Aktivieren von erforderlich `QueryInterface`.

## <a name="members"></a>Member

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ImplementsHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)