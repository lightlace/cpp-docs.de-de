---
title: Globale Funktionen COM-Zuordnung | Microsoft-Dokumentation
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c37f722267107ad06fb51dc78bd682603161a476
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-global-functions"></a>Globale Funktionen COM-Zuordnung
Diese Funktionen bieten Unterstützung für COM-Zuordnung **IUnknown** Implementierungen.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Delegiert an die **IUnknown** eines zusammengesetzten Objekts.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Generiert effizienten Code für den Vergleich von Schnittstellen mit **IUnknown**.|  

  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="a-nameatlinternalqueryinterfacea--atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
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
 [in] Ein Array von **_ATL_INTMAP_ENTRY** -Strukturen, die eine Übersicht über die verfügbaren Schnittstellen zuzugreifen.  
  
 `iid`  
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlInternalQueryInterface`behandelt nur Schnittstellen im COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `AtlInternalQueryInterface` wird nicht an die äußere unbekannte delegieren. Sie können die Schnittstellen in der COM-Zuordnungstabelle mit dem Makro eingeben [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) oder einer seiner Varianten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#94;](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="a-nameinlineisequaliunknowna--inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 Rufen Sie diese Funktion, speziellen Test auf **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Parameter  
 *rguid1*  
 [in] Die GUID für den Vergleich **IID_IUnknown**.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Makros für COM-Zuordnung](../../atl/reference/com-map-macros.md)

