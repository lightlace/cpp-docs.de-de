---
title: messages_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: b8fe1ab2db792819831f5c50aa99a02559f71cdd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451804"
---
# <a name="messagesbyname-class"></a>messages_byname-Klasse

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Meldungsfacet eines angegebenen Gebietsschemas dienen kann und das Abrufen von lokalisierten Meldungen ermöglicht.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>Parameter

*_Locname*\
Ein benanntes Gebietsschema.

*_Refs*\
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das benannte Gebiets Schema *_Locname*festgelegt. Jeder Konstruktor initialisiert sein Basisobjekt mit [messages](../standard-library/messages-class.md#messages)\<CharType>(`_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
