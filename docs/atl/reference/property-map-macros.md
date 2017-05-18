---
title: Eigenschaftenmakros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fbbed22766f9029456f15c4a554ae91322e6a275
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="property-map-macros"></a>Eigenschaftenmakros
Diese Makros definieren eigenschaftenzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|Markiert den Beginn der Zuordnung ATL-Eigenschaft.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|Gibt den Umfang oder die Dimensionen eines ActiveX-Steuerelements.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|Gibt eine Beschreibung, die DISPID-Eigenschaft und die Eigenschaft Eigenschaftenseite CLSID in dar.|  
|[PROP_ENTRY_TYPE_EX ZU](#prop_entry_type_ex)|Gibt eine Beschreibung der Eigenschaft, Eigenschaft DISPID Eigenschaftenseite CLSID und `IDispatch` IID in dar.|  
|[PROP_PAGE](#prop_page)|Gibt eine Eigenschaftenseite CLSID in dar.|  
|[END_PROP_MAP](#end_prop_map)|Markiert das Ende der Zuordnung ATL-Eigenschaft.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
   
##  <a name="begin_prop_map"></a>BEGIN_PROP_MAP  
 Markiert den Anfang des Objekts Eigenschaft Zuordnung.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Gibt die Klasse, die eigenschaftszuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die eigenschaftenzuordnung Eigenschaft DISPIDs, Eigenschaftenseite CLSIDs, die Beschreibung der Eigenschaften speichert und `IDispatch` IIDs. Klassen [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), und [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) eigenschaftszuordnung abrufen und diese Informationen verwenden.  
  
 Wenn Sie ein Objekt mit dem Assistenten für ATL-Projekt erstellen, der Assistent erstellt eine Zuordnung empty-Eigenschaft durch Angabe `BEGIN_PROP_MAP` gefolgt von [END_PROP_MAP](#end_prop_map).  
  
 `BEGIN_PROP_MAP`wird nicht, das Ausmaß (d. h. die Dimensionen) einer Zuordnung Eigenschaft gespeichert werden, da ein Objekt mit einer eigenschaftszuordnung keine Benutzeroberfläche, damit kein Block werden müssten. Wenn das Objekt ein ActiveX-Steuerelement mit einer Benutzeroberfläche ist, hat es einen Block. In diesem Fall geben Sie [PROP_DATA_ENTRY](#prop_data_entry) in Ihrer eigenschaftszuordnung den Wertebereich angeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#103;](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>PROP_DATA_ENTRY  
 Gibt den Umfang oder die Dimensionen eines ActiveX-Steuerelements.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Beschreibung der Eigenschaft.  
  
 `member`  
 [in] Der Datenmember, die den Wertebereich enthält; beispielsweise `m_sizeExtent`.  
  
 *VT*  
 [in] Gibt den VARIANT-Typ der Eigenschaft an.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird den angegebenen Datenmember beibehalten werden.  
  
 Wenn Sie ein ActiveX-Steuerelement erstellen, fügt der Assistent dieses Makro nach dem Eigenschaft-Map-Makro [BEGIN_PROP_MAP](#begin_prop_map) und vor der Zuordnung Eigenschaftenmakro [END_PROP_MAP](#end_prop_map).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel, das Ausmaß des Objekts ( `m_sizeExtent`) wird persistent gespeichert wird.  
  
 [!code-cpp[NVC_ATL_Windowing&#131;](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#132;](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>PROP_ENTRY_TYPE  
 Verwenden Sie dieses Makro, eine Beschreibung, die DISPID-Eigenschaft und die Eigenschaft Eigenschaftenseite CLSID in die Objekttabelle Eigenschaft eingeben.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Beschreibung der Eigenschaft.  
  
 `dispid`  
 [in] Die Eigenschaft DISPID.  
  
 `clsid`  
 [in] Die CLSID der zugeordneten Seite. Verwenden den speziellen Wert `CLSID_NULL` für eine Eigenschaft, die nicht über eine zugehörige Eigenschaftenseite verfügt.  
  
 `vt`  
 [in] Der Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `PROP_ENTRY` Makro wurde unsicher und veraltet. Es wurde durch ersetzt `PROP_ENTRY_TYPE`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang dar; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).  
  
##  <a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX ZU  
 Ähnlich wie [PROP_ENTRY_TYPE](#prop_entry_type), jedoch können Sie eine bestimmte IID angeben, wenn das Objekt mehrere duale Schnittstellen unterstützt.  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>Parameter  
 `szDesc`  
 [in] Beschreibung der Eigenschaft.  
  
 `dispid`  
 [in] Die Eigenschaft DISPID.  
  
 `clsid`  
 [in] Die CLSID der zugeordneten Seite. Verwenden den speziellen Wert `CLSID_NULL` für eine Eigenschaft, die nicht über eine zugehörige Eigenschaftenseite verfügt.  
  
 `iidDispatch`  
 [in] Die IID der dualen Schnittstelle definiert.  
  
 `vt`  
 [in] Der Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `PROP_ENTRY_EX` Makro wurde unsicher und veraltet. Es wurde durch ersetzt `PROP_ENTRY_TYPE_EX`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang dar; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel werden Einträge für `IMyDual1` gefolgt von einem Eintrag für `IMyDual2`. Gruppieren nach duale Schnittstelle wird die Leistung verbessert.  
  
 [!code-cpp[NVC_ATL_Windowing&#133;](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>PROP_PAGE  
 Verwenden Sie dieses Makro, um eine Eigenschaftenseite CLSID in die Objekttabelle Eigenschaft einzugeben.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID einer Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 `PROP_PAGE`ähnelt dem [PROP_ENTRY_TYPE](#prop_entry_type), aber eine Beschreibung der Eigenschaft oder DISPID ist nicht erforderlich.  
  
> [!NOTE]
>  Wenn Sie bereits eine CLSID mit `PROP_ENTRY_TYPE` oder [PROP_ENTRY_TYPE_EX zu](#prop_entry_type_ex), Sie müssen keine zusätzlichen Eintrag mit `PROP_PAGE`.  
  
 Die [BEGIN_PROP_MAP](#begin_prop_map) Makro kennzeichnet den Anfang dar; das [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#134;](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>END_PROP_MAP  
 Markiert das Ende des Objekts eigenschaftszuordnung.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt mit dem Assistenten für ATL-Projekt erstellen, der Assistent erstellt eine Zuordnung empty-Eigenschaft durch Angabe [BEGIN_PROP_MAP](#begin_prop_map) gefolgt von `END_PROP_MAP`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

