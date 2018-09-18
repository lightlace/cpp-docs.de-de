---
title: CInterfaceList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac378e0a923e2a906bf99995432bfc87e39b8d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032431"
---
# <a name="cinterfacelist-class"></a>CInterfaceList-Klasse

Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste der COM-Schnittstellenzeiger zu erstellen.

## <a name="syntax"></a>Syntax

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Parameter

*I*<br/>
Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.

*piid*<br/>
Ein Zeiger auf die IID der *ich*.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Der Konstruktor für die Schnittstellenliste.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor und die abgeleiteten Methoden zum Erstellen einer Liste von COM-Schnittstellenzeiger. Verwendung [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) Wenn ein Array erforderlich ist.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList

Der Konstruktor für die Schnittstellenliste.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße hat den Standardwert 10.

### <a name="remarks"></a>Hinweise

Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

## <a name="see-also"></a>Siehe auch

[CAtlList-Klasse](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
