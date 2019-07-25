---
title: moneypunct_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: 47c9d2281973cb57288bfdcf865926fb6dd9ed0e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460208"
---
# <a name="moneypunctbyname-class"></a>moneypunct_byname-Klasse

Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als `moneypunct`-Facet eines bestimmten Gebietsschemas dienen kann und die Formatierung von monetären Ein- und Ausgabefeldern ermöglicht.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das benannte Gebietsschema `_Locname` bestimmt. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
