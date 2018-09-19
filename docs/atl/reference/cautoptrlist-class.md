---
title: CAutoPtrList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c33c3524d0fb6b39208e2cb7be57805a3ff043f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046757"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList-Klasse

Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste von intelligenten Zeigern zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parameter

*E*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Der Konstruktor.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor bereit und leitet Sie Methoden aus [CAtlList](../../atl/reference/catllist-class.md) und [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) zur Unterstützung der Erstellung eines Listenobjekts intelligente Zeiger speichern. Die Klasse [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) bietet eine ähnliche Funktion für ein Arrayobjekt.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cautoptrlist"></a>  CAutoPtrList::CAutoPtrList

Der Konstruktor.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße hat den Standardwert 10.

### <a name="remarks"></a>Hinweise

Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

## <a name="see-also"></a>Siehe auch

[CAtlList-Klasse](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits-Klasse](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
