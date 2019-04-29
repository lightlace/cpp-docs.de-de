---
title: to_vector-Funktion
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 4fa4e9c620519cc6bb2f96d346ded88b6cc826ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404623"
---
# <a name="tovector-function"></a>to_vector-Funktion

Gibt `std::vector` zurück, dessen Wert der Auflistung entspricht, die dem angegebenen IVector- oder IVectorView-Parameter zugrunde liegt.

## <a name="syntax"></a>Syntax

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Vorlagentyp-Parameter.

*v*<br/>
Eine IVector- oder IVectorView-Schnittstelle, die Zugriff auf ein zugrunde liegendes Vektor- oder VectorView-Objekt bietet.

### <a name="return-value"></a>Rückgabewert

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Windows::Foundation::Collections

## <a name="see-also"></a>Siehe auch

[Windows::Foundation::Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
