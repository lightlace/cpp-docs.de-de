---
title: numpunct_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: 0c9eb565c2dbf54da449411aa11a4c5661debf1d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452318"
---
# <a name="numpunctbyname-class"></a>numpunct_byname-Klasse

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als `numpunct`-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung und Interpunktion von numerischen und booleschen Ausdrücken ermöglicht.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das [named](../standard-library/locale-class.md#name)-Gebietsschema `_Locname` bestimmt. Der Konstruktor initialisiert sein Basisobjekt mit [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>(`_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
