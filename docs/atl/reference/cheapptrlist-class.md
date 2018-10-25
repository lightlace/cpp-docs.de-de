---
title: CHeapPtrList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56dad973f415fa4944bd4561dab94636e10e6539
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058920"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList-Klasse

Diese Klasse stellt nützliche Methoden beim Erstellen einer Liste von Heap-Zeigern.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>Parameter

*E*<br/>
Der Objekttyp in der Auflistungsklasse gespeichert werden.

*Zuweisung*<br/>
Die Speicher-Allocation-Klasse verwenden. Der Standardwert ist [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Der Konstruktor.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor bereit und leitet Sie Methoden aus [CAtlList](../../atl/reference/catllist-class.md) und [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) zur Unterstützung der Erstellung eines Klassenobjekts Collection Heap Zeiger speichern.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cheapptrlist"></a>  CHeapPtrList::CHeapPtrList

Der Konstruktor.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße.

### <a name="remarks"></a>Hinweise

Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

## <a name="see-also"></a>Siehe auch

[CAtlList-Klasse](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrElementTraits-Klasse](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
