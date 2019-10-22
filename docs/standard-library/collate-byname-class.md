---
title: collate_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 3e9a256ac7bdb5f6d077746fe2a08990ed41e931
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688273"
---
# <a name="collate_byname-class"></a>collate_byname-Klasse

Eine abgeleitete Klassen Vorlage, die ein Objekt beschreibt, das als COLLATE-Facette eines bestimmten Gebiets Schemas fungieren kann. Dies ermöglicht das Abrufen von Informationen, die für einen Kulturbereich in Bezug auf Zeichen folgen Sortier Konventionen gelten.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>Parameter

*_Locname* \
Ein benanntes Gebietsschema.

*_Refs* \
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage [wird ein Objekt](../standard-library/locale-class.md#facet_class) beschrieben, das als Gebiets Schema des Typs [COLLATE](../standard-library/collate-class.md#collate) \<CharType > fungieren kann. Das Verhalten wird durch das [benannte](../standard-library/locale-class.md#name) Gebiets Schema *_Locname*festgelegt. Jeder Konstruktor initialisiert sein Basisobjekt mit [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
