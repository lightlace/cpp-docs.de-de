---
title: Globale COM-Zuordnungs-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d3db2a3d7f673c8e81b1077bcb45e9b8241d37
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751860"
---
# <a name="com-map-global-functions"></a>Globale COM-Zuordnungs-Funktionen

Diese Funktionen bieten Unterstützung für COM-Zuordnung `IUnknown` Implementierungen.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Delegiert an die `IUnknown` eines zusammengesetzten Objekts.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Generiert von effizientem Code für den Vergleich von Schnittstellen für `IUnknown`.|  

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Parameter

*pThis*  
[in] Ein Zeiger auf das Objekt, das die Zuordnung der COM-Schnittstellen verfügbar gemacht werden, um enthält `QueryInterface`.

*pEntries*  
[in] Ein Array von `_ATL_INTMAP_ENTRY` Strukturen, die auf eine Karte der verfügbaren Schnittstellen zugreifen.

*IID*  
[in] Die GUID der Schnittstelle angefordert wird.

*ppvObject*  
[out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

`AtlInternalQueryInterface` behandelt nur Schnittstellen in der COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `AtlInternalQueryInterface` ist das nicht an die äußere unbekannte delegieren. Sie können Schnittstellen eingeben, in die COM-Zuordnungstabelle mit dem Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oder eine ihrer Varianten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown

Rufen Sie diese Funktion, für die speziellen Test für `IUnknown`.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Parameter

*rguid1*  
[in] Die GUID, der zu vergleichende `IID_IUnknown`.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)   
[COM-Zuordnungs-Makros](../../atl/reference/com-map-macros.md)
