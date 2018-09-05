---
title: ICollectionOnSTLImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bbfb34d34f6bd920744621042f5f3e09143e896
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751318"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl-Klasse

Diese Klasse stellt die Methoden, die von einer Auflistungsklasse.

## <a name="syntax"></a>Syntax

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>  
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Parameter

*T*  
Eine Schnittstelle für den COM-Auflistung.

*CollType*  
Eine C++-Standardbibliothek-Container-Klasse.

*ItemType*  
Der Typ des Elements, die von der Containerschnittstelle verfügbar gemacht werden.

*CopyItem*  
Ein [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).

*EnumType*  
Ein [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)-kompatiblen Enumerator-Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Gibt ein Enumeratorobjekt für die Sammlung zurück.|
|[ICollectionOnSTLImpl::getcount](#get_count)|Gibt die Anzahl der Elemente in der Auflistung zurück.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|Gibt das angeforderte Element aus der Auflistung zurück.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Die Auflistung.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt die Implementierung für drei Methoden einer Schnittstelle für die Sammlung: [Getcount](#get_count), [Get_Item](#get_item), und [Get__NewEnum](#newenum).

Diese Klasse verwenden zu können:

- Definieren, oder leihen eine Collection-Schnittstelle, die Sie implementieren möchten.

- Leiten Sie eine Klasse aus einer Spezialisierung von `ICollectionOnSTLImpl` basierend auf diese Auflistungsschnittstelle.

- Verwenden Sie die abgeleitete Klasse zum Implementieren von Methoden aus der Auflistungsschnittstelle, die von nicht verarbeitet `ICollectionOnSTLImpl`.

> [!NOTE]
>  Leiten Sie eine Klasse aus, wenn die Auflistung eine duale Schnittstelle wird, [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), und übergeben Sie die `ICollectionOnSTLImpl` Spezialisierung als der erste Vorlagenparameter ATL, um die Implementierung der Wunsch der `IDispatch` -Methoden.

- Hinzufügen von Elementen, die [M_coll](#m_coll) Member zum Auffüllen der Auflistung.

Weitere Informationen und Beispiele finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="get_count"></a>  ICollectionOnSTLImpl::getcount

Diese Methode gibt die Anzahl der Elemente in der Auflistung zurück.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Parameter

*pcount*  
[out] Die Anzahl der Elemente in der Auflistung.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="get_item"></a>  ICollectionOnSTLImpl::get_Item

Diese Methode gibt das angegebene Element aus der Auflistung zurück.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Parameter

*Index*  
[in] Der 1-basierten Index eines Elements in der Auflistung.

*pvar*  
[out] Das Element, das entspricht *Index*.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Der Artikel erhalten Sie durch Kopieren der Daten an der angegebenen Position in [M_coll](#m_coll) mit der Copy-Methode, der die [Richtlinienklasse kopieren](../../atl/atl-copy-policy-classes.md) übergeben als Vorlagenargument in die `ICollectionOnSTLImpl` Spezialisierung.

##  <a name="newenum"></a>  ICollectionOnSTLImpl::get__NewEnum

Gibt ein Enumeratorobjekt für die Sammlung zurück.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Parameter

*ppUnk*  
[out] Die **IUnknown** Zeiger von einem neu erstellten Enumerator-Objekt.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Der neu erstellte Enumerator verwaltet einen Iterator für die ursprüngliche Auflistung `m_coll`, (also keine Kopie erstellt wird) und hält Sie einen COM-Verweis für das Sammlungsobjekt, um sicherzustellen, dass die Auflistung aktiv bleibt, während es ausstehende Enumeratoren sind.

##  <a name="m_coll"></a>  ICollectionOnSTLImpl::m_coll

Dieses Element enthält die Elemente der Auflistung dargestellt.

```
CollType m_coll;
```

## <a name="see-also"></a>Siehe auch

[-Beispiel](../../visual-cpp-samples.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
