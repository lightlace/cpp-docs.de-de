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
ms.openlocfilehash: 5a3a31125d8489551f1eec143013661bf385f29a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212444"
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

[Referenz (Windows-Runtime-Bibliothek)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)