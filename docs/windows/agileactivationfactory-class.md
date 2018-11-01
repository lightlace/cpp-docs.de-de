---
title: AgileActivationFactory-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::AgileActivationFactory
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
ms.openlocfilehash: 941e135cb1b6c90d6ccf858a576cf1d0b055970f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649864"
---
# <a name="agileactivationfactory-class"></a>AgileActivationFactory-Klasse

Stellt eine geeignete Apartment aktivierungsfactory, die implementiert [FtmBase](../windows/ftmbase-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    FactoryCacheFlags cacheFlagValue = FactoryCacheDefault
>
class AgileActivationFactory :
    public ActivationFactory<
        Implements<FtmBase, I0>,
        I1,
        I2,
        cacheFlagValue
    >;
```

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)<br/>
[ActivationFactory-Klasse](../windows/activationfactory-class.md)