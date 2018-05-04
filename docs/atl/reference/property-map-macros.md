---
title: Eigenschaft Zuordnungsmakros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 718028385b3910b955c49ab9e0abddf23b443967
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="property-map-macros"></a>Eigenschaft Ereigniszuordnungs-Makros
Diese Makros definieren eigenschaftenzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|Markiert den Beginn der Zuordnung ATL-Eigenschaft.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|Gibt den Block oder Dimensionen, der ein ActiveX-Steuerelement.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|Eine Beschreibung, die DISPID-Eigenschaft und die Eigenschaft Eigenschaftenseite CLSID wird in der eigenschaftenzuordnung gelangt.|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Gibt eine Beschreibung der Eigenschaft, Eigenschaft DISPID Eigenschaftenseite CLSID und `IDispatch` IID in die eigenschaftenzuordnung.|  
|[PROP_PAGE](#prop_page)|Eine Eigenschaftenseite CLSID wird in der eigenschaftenzuordnung gelangt.|  
|[END_PROP_MAP](#end_prop_map)|Markiert das Ende der Zuordnung ATL-Eigenschaft.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP  
 Markiert den Beginn der objektzuordnung-Eigenschaft.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Gibt die Klasse, die eigenschaftenzuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die eigenschaftenzuordnung speichert Eigenschaft DISPIDs, Eigenschaftenseite CLSIDs, die Beschreibung der Eigenschaften und `IDispatch` IIDs. Klassen [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), und [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)die eigenschaftenzuordnung abgerufen, und legen Sie diese Informationen verwenden.  
  
 Wenn Sie ein Objekt mit dem ATL-Projekt-Assistenten erstellen, erstellt der Assistent eine Zuordnung für die Eigenschaft "empty" auf, durch Angeben von `BEGIN_PROP_MAP` gefolgt von [END_PROP_MAP](#end_prop_map).  
  
 `BEGIN_PROP_MAP` werden nicht aus dem Wertebereich (d. h. der Dimensionen), eine eigenschaftenzuordnung gespeichert werden, da ein Objekt mithilfe einer eigenschaftenzuordnung nicht Benutzeroberfläche, möglicherweise, daher müssen keine Block würden. Wenn das Objekt ein ActiveX-Steuerelement mit einer Benutzeroberfläche ist, muss es sich um ein Block. In diesem Fall müssen Sie angeben [PROP_DATA_ENTRY](#prop_data_entry) in Ihrer eigenschaftenzuordnung den Wertebereich angeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY  
 Gibt den Block oder Dimensionen, der ein ActiveX-Steuerelement.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Die Beschreibung der Eigenschaft.  
  
 `member`  
 [in] Das Datenelement, das den Wertebereich enthält; beispielsweise `m_sizeExtent`.  
  
 *vt*  
 [in] Gibt den VARIANT-Datentyp der Eigenschaft an.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro führt den angegebenen Datenmember beibehalten werden.  
  
 Wenn Sie ein ActiveX-Steuerelement erstellen, fügt der Assistent dieses Makro nach der Eigenschaft Zuordnungsmakros [BEGIN_PROP_MAP](#begin_prop_map) und vor der Eigenschaft Zuordnungsmakros [END_PROP_MAP](#end_prop_map).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel, das Ausmaß des Objekts ( `m_sizeExtent`) wird persistent gespeichert werden.  
  
 [!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE  
 Verwenden Sie dieses Makro, um eine Beschreibung, die DISPID-Eigenschaft und die Eigenschaft Eigenschaftenseite CLSID in der objektzuordnung Eigenschaft einzugeben.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Die Beschreibung der Eigenschaft.  
  
 `dispid`  
 [in] Die Eigenschaft DISPID.  
  
 `clsid`  
 [in] Die CLSID der zugehörigen Eigenschaftenseite. Verwenden den speziellen Wert `CLSID_NULL` für eine Eigenschaft, die nicht über eine Eigenschaftenseite des zugehörigen verfügt.  
  
 `vt`  
 [in] Der Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `PROP_ENTRY` Makro wurde als unsicher und veraltet. Es wurde durch ersetzt `PROP_ENTRY_TYPE`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang der eigenschaftenzuordnung; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).  
  
##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX  
 Ähnlich wie [PROP_ENTRY_TYPE](#prop_entry_type), jedoch können Sie eine bestimmte IID angeben, wenn das Objekt mehrere duale Schnittstellen unterstützt.  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Die Beschreibung der Eigenschaft.  
  
 `dispid`  
 [in] Die Eigenschaft DISPID.  
  
 `clsid`  
 [in] Die CLSID der zugehörigen Eigenschaftenseite. Verwenden den speziellen Wert `CLSID_NULL` für eine Eigenschaft, die nicht über eine Eigenschaftenseite des zugehörigen verfügt.  
  
 `iidDispatch`  
 [in] Die IID der dualen Schnittstelle definieren die Eigenschaft.  
  
 `vt`  
 [in] Der Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `PROP_ENTRY_EX` Makro wurde als unsicher und veraltet. Es wurde durch ersetzt `PROP_ENTRY_TYPE_EX`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang der eigenschaftenzuordnung; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel gruppiert die Einträge für `IMyDual1` gefolgt von einem Eintrag für `IMyDual2`. Gruppierung nach duale Schnittstelle wird die Leistung verbessert.  
  
 [!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>  PROP_PAGE  
 Verwenden Sie dieses Makro, um eine Eigenschaftsseite CLSID in der objektzuordnung Eigenschaft einzugeben.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID einer Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 `PROP_PAGE` ähnelt dem [PROP_ENTRY_TYPE](#prop_entry_type), aber eine Beschreibung der Eigenschaft oder die DISPID ist nicht erforderlich.  
  
> [!NOTE]
>  Wenn Sie bereits mit CLSID `PROP_ENTRY_TYPE` oder [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), müssen Sie keine zusätzlichen Eintrag mit `PROP_PAGE`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang der eigenschaftenzuordnung; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>  END_PROP_MAP  
 Markiert das Ende der objektzuordnung-Eigenschaft.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt mit dem ATL-Projekt-Assistenten erstellen, erstellt der Assistent eine Zuordnung für die Eigenschaft "empty" auf, durch Angeben von [BEGIN_PROP_MAP](#begin_prop_map) gefolgt von `END_PROP_MAP`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
