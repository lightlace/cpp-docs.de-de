---
title: DerefHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 7e9de446fdf18b3cf92cc438e421287c8fcfc29f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450195"
---
# <a name="derefhelper-structure"></a>DerefHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Vorlagenparameter.

## <a name="remarks"></a>Hinweise

Einen dereferenzierter Zeiger zum Darstellen der `T*` Template-Parameter.

**DerefHelper** wie z. B. in einem Ausdruck verwendet wird: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`DerefType`|Bezeichner für den Vorlagenparameter von dereferenziert `T*`.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`DerefHelper`

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)