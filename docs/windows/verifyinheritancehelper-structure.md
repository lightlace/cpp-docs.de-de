---
title: VerifyInheritanceHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a7b101091cefcdca65518c2a62bd274f7af4607
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610254"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename I,
   typename Base
>
struct VerifyInheritanceHelper;
template <
   typename I
>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parameter

*I*  
Ein Typ.

*Basis*  
Einen anderen Typ.

## <a name="remarks"></a>Hinweise

Testet, ob eine Schnittstelle, die von einer anderen Schnittstelle abgeleitet wird.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[VerifyInheritanceHelper::Verify-Methode](../windows/verifyinheritancehelper-verify-method.md)|Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VerifyInheritanceHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)