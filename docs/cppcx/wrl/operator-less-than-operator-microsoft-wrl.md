---
title: 'Operator&lt; -Operator (Microsoft:: wrl)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 4887a7ebf3906edbc4a5a2a723caff0ad7732c46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182924"
---
# <a name="operatorlt-operator-microsoftwrl"></a>Operator&lt; -Operator (Microsoft:: wrl)

Bestimmt, ob die Adresse eines Objekts kleiner als ein anderes ist.

## <a name="syntax"></a>Syntax

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Parameter

*a*<br/>
Das linke Objekt.

*b*<br/>
Das rechte Objekt.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die Adresse des *eine* ist kleiner als die Adresse des *b*ist, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)