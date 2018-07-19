---
title: codecvt_byname-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_byname
dev_langs:
- C++
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 822d19e1333163dbe37a1734ce315048f81cb802
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964371"
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

*_Locname* ein benanntes Gebietsschema.

*_Refs* eine Initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Byname-Facets werden automatisch erstellt, wenn ein benanntes Gebietsschema erstellt wird.

Das Verhalten wird durch das benannte Gebietsschema bestimmt *_Locname*. Jeder Konstruktor initialisiert sein Basisobjekt mit [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
