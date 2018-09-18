---
title: CAutoPtrArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23cc8e519fc47173efe413cc687ef48c0dc39945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025164"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray-Klasse

Diese Klasse stellt die Methoden, die nützlich, wenn Sie ein Array von intelligenten Zeigern zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parameter

*E*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Der Konstruktor.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor bereit und leitet Sie Methoden aus [CAtlArray](../../atl/reference/catlarray-class.md) und [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) zur Unterstützung der Erstellung eines Klassenobjekts Auflistung Speichern von intelligenten Zeigern.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray

Der Konstruktor.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert den intelligenten Zeiger-Array.

## <a name="see-also"></a>Siehe auch

[CAtlArray-Klasse](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits-Klasse](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList-Klasse](../../atl/reference/cautoptrlist-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
