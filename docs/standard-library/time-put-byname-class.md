---
title: time_put_byname-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34ac10a6456c2bc1b69d3076e5b3ba351507c3ee
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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

`_Locname` Eine Gebietsschemanamen.

`_Refs` Ein Verweiszähler.

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das [named](../standard-library/locale-class.md#name)-Gebietsschema `_Locname` bestimmt. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator>( `_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
