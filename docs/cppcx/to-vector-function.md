---
title: To_vector-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3dcccc332a5d768a614414838003e1400f3c6a6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107626"
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

[Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)