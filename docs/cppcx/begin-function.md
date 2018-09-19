---
title: BEGIN-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad73daba0bce57a19c512a53747cf8ac804e929d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101754"
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

[Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)