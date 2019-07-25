---
title: codecvt_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: 62781d575d6b9dda3f3c1e2a744091221c6f9584
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459854"
---
# <a name="codecvtbyname-class"></a>codecvt_byname-Klasse

Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konvertierungen abgerufen werden können.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```

```cpp
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```

```cpp
protected:
    virtual ~codecvt_byname();

};
```

### <a name="parameters"></a>Parameter

*_Locname*\
Ein benanntes Gebietsschema.

*_Refs*\
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Byname-Facets werden automatisch erstellt, wenn ein benanntes Gebietsschema erstellt wird.

Das Verhalten wird durch das benannte Gebiets Schema *_Locname*festgelegt. Jeder Konstruktor initialisiert sein Basisobjekt mit [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
