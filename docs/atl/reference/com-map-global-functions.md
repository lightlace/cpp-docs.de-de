---
title: "Globale Funktionen für COM-Zuordnung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: d6f23de1a5fd13d61d376acded35f9217d0a898d
ms.lasthandoff: 03/31/2017

---
# <a name="com-map-global-functions"></a>COM-Zuordnung globale Funktionen
Diese Funktionen bieten Unterstützung für COM-Zuordnung **IUnknown** Implementierungen.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Delegiert an die **IUnknown** eines zusammengesetzten Objekts.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Generiert von effizientem Code zum Vergleichen von Schnittstellen für **IUnknown**.|  

  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pThis`  
 [in] Ein Zeiger auf das Objekt mit der COM-Zuordnung von Schnittstellen verfügbar gemacht werden, um `QueryInterface`.  
  
 `pEntries`  
 [in] Ein Array von **_ATL_INTMAP_ENTRY** Strukturen, die eine Übersicht der verfügbaren Schnittstellen zuzugreifen.  
  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlInternalQueryInterface`nur behandelt Schnittstellen in der COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `AtlInternalQueryInterface` delegieren, die äußere unbekannte nicht. Geben Sie den Schnittstellen, in der COM-Zuordnungstabelle mit dem Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oder einer dessen Varianten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing #94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 Rufen Sie diese Funktion speziellen Test auf **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Parameter  
 *rguid1*  
 [in] Die GUID für den Vergleich **IID_IUnknown**.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [COM-Zuordnungs-Makros](../../atl/reference/com-map-macros.md)

