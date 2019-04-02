---
title: Move-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 1a03216197462090f38d3bc2065fe227f0667919
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785316"
---
# <a name="move-function"></a>Move-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Arguments.

*arg*<br/>
Ein Argument zu verschieben.

## <a name="return-value"></a>Rückgabewert

Parameter *Arg* nach Verweis "oder" Rvalue-Verweis "traits", sofern vorhanden, wurden entfernt.

## <a name="remarks"></a>Hinweise

Verschiebt das angegebene Argument von einem Speicherort.

Weitere Informationen finden Sie unter den **verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)