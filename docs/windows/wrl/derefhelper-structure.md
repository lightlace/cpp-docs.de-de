---
title: DerefHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 7709ae63e4d49e25aec83a069ad1ac614bfbd953
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335953"
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

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)