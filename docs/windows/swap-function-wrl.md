---
title: Swap-Funktion (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
ms.openlocfilehash: daa5ab94146866dfa8f1983afc1ad7b37cdb6b06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476407"
---
# <a name="swap-function-wrl"></a>Swap-Funktion (WRL)

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste Argument.

*right*<br/>
Das zweite Argument.

## <a name="return-value"></a>Rückgabewert

## <a name="remarks"></a>Hinweise

Tauscht die Werte der beiden angegebenen Argumente.

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)