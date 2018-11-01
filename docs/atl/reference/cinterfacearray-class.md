---
title: CInterfaceArray-Klasse
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: 64271cbdb634284a5abcdd17b2c14d23a496b3f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614249"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray-Klasse

Diese Klasse stellt nützliche Methoden aus, wenn Sie ein Array von COM-Schnittstellenzeiger zu erstellen.

## <a name="syntax"></a>Syntax

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Der Konstruktor für das schnittstellenarray.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor und die abgeleiteten Methoden zum Erstellen eines Arrays von COM-Schnittstellenzeiger. Verwendung [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Wenn eine Liste erforderlich ist.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray

Der Konstruktor.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert den intelligenten Zeiger-Array.

## <a name="see-also"></a>Siehe auch

[CAtlArray-Klasse](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr-Klasse](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
