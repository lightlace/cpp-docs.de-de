---
title: time_put_byname-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62d78fb7c2b9cbaee62baf59636303f90177cf7b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699594"
---
# <a name="timeputbyname-class"></a>time_put_byname-Klasse

Diese abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet vom Typ `time_put`\< CharType, OutputIterator > dienen kann.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>Parameter

*_Locname*<br/>
Name eines Gebietsschemas.

*_Refs*<br/>
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Das Verhalten richtet sich nach der [mit dem Namen](../standard-library/locale-class.md#name) Gebietsschema *_Locname*. Jeder Konstruktor initialisiert sein Basisobjekt mit [Time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator > (`_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
