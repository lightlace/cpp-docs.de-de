---
title: ctype_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: 0b0f33781cc9f1f54661a44a5434c94316432a45
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457899"
---
# <a name="ctypebyname-class"></a>ctype_byname-Klasse

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als ctype-Facet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen sowie die Konvertierung von Zeichen zwischen Groß-/Kleinschreibung und zwischen nativen und gebietsschemaspezifischen Zeichensätzen ermöglicht.

## <a name="syntax"></a>Syntax

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das benannte Gebietsschema `_Locname` bestimmt. Jeder Konstruktor initialisiert sein Basisobjekt mit [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) oder der jeweiligen Entsprechung für die Basisklasse `ctype<char>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
