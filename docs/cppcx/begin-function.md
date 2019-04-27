---
title: begin-Funktion
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: 1b95e4d32321aadf7de65ecb25109fbecd9eb614
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258290"
---
# <a name="begin-function"></a>begin-Funktion

Gibt einen Iterator zurück, der an den Anfang einer Auflistung zeigt, auf die über den angegebenen Schnittstellenparameter zugegriffen wird.

## <a name="syntax"></a>Syntax

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ein Vorlagentyp-Parameter.

*v*<br/>
Eine Auflistung von Vektor\<T >- oder VectorView\<T >-Objekten, die durch eine IVector erfolgt\<T > oder IVectorView\<T >-Schnittstelle.

*i*<br/>
Eine Auflistung von beliebigen Windows-Runtime-Objekten, die von einer IIterable zugegriffen wird\<T >-Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der zum Anfang der Auflistung zeigt.

### <a name="remarks"></a>Hinweise

Die ersten beiden Vorlagenfunktionen geben Iteratoren zurück und die dritte Vorlagenfunktion gibt einen Eingabeiterator zurück.

Der VectorIterator-Objekt, das von zurückgegebene beginnen ist ein proxyiterator, der Elemente des Typs VectorProxy speichert\<T >. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Windows::Foundation::Collections

## <a name="see-also"></a>Siehe auch

[Windows::Foundation::Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
