---
title: '&lt;sstream&gt; Funktionen'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: f22aec854b9a1d9b7b8360cacbb08760413fa22e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412513"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; Funktionen

||
|-|
|[swap](#sstream_swap)|

## <a name="sstream_swap"></a>  swap

Tauscht die Werte zwischen zwei `sstream`-Objekten aus.

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Verweis auf ein `sstream`-Objekt.|
|*right*|Ein Verweis auf ein `sstream`-Objekt.|

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt `left.swap(right)` aus.

## <a name="see-also"></a>Siehe auch

[\<sstream>](../standard-library/sstream.md)<br/>
