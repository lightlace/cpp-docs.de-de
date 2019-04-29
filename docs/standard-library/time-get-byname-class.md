---
title: time_get_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: e18f210dba03d66fa3a4ea111a6dfc61f0d0c12a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412006"
---
# <a name="timegetbyname-class"></a>time_get_byname-Klasse

Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet vom Typ `time_get`\<CharType, InputIterator> dienen kann.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>Parameter

*_Locname*<br/>
Ein benanntes Gebietsschema.

*_Refs*<br/>
Eine initiale Verweisanzahl.

## <a name="requirements"></a>Anforderungen

Das Verhalten wird durch das benannte Gebietsschema bestimmt *_Locname*. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
