---
title: codecvt_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: b48f01126eba7082230fc5e19150d42d1dfad2f3
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688292"
---
# <a name="codecvt_byname-class"></a>codecvt_byname-Klasse

Eine abgeleitete Klassen Vorlage, die ein Objekt beschreibt, das als COLLATE-Facette eines bestimmten Gebiets Schemas fungieren kann. Dies ermöglicht das Abrufen von Informationen, die für einen kulturellen Bereich in Bezug auf Konvertierungen spezifisch sind

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

*_Locname* \
Ein benanntes Gebietsschema.

*_Refs* \
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Byname-Facets werden automatisch erstellt, wenn ein benanntes Gebietsschema erstellt wird.

Das Verhalten wird durch das benannte Gebiets Schema *_Locname*festgelegt. Jeder Konstruktor initialisiert sein Basisobjekt mit [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
