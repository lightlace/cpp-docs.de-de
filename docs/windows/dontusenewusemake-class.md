---
title: DontUseNewUseMake-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ce3e391ac0da93ed7571a95ce328a5260a8dd44
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593606"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Hinweise

Verhindert die Verwendung von Operator **neue** in `RuntimeClass`. Folglich müssen Sie verwenden die [Funktion](../windows/make-function.md) stattdessen.

## <a name="members"></a>Member

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[DontUseNewUseMake::operator new-Operator](../windows/dontusenewusemake-operator-new-operator.md)|Überlädt **neue** und verhindert, dass deren verwendeten `RuntimeClass`.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`DontUseNewUseMake`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)  
[Make-Funktion](../windows/make-function.md)