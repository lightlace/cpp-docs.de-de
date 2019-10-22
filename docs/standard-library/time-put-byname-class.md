---
title: time_put_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: 4471c0df352a4d40d863ac36f0245cf8194f588c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685468"
---
# <a name="time_put_byname-class"></a>time_put_byname-Klasse

In der abgeleiteten Klassen Vorlage wird ein Objekt beschrieben, das als Gebiets Schema-Facette vom Typ `time_put` \< CharType, OutputIterator > fungieren kann.

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

*_Locname* \
Name eines Gebietsschemas.

*_Refs* \
Eine initiale Verweisanzahl.

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das [benannte](../standard-library/locale-class.md#name) Gebiets Schema *_Locname*festgelegt. Jeder Konstruktor initialisiert sein Basisobjekt mit [Time_put](../standard-library/time-put-class.md#time_put) \<CharType, OutputIterator > (`_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
