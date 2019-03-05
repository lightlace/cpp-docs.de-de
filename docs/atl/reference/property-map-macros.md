---
title: Eigenschaftenzuordnungs-Makros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 1e2e7235dd924467d9d5e0613a704fedf8340ae4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264897"
---
# <a name="property-map-macros"></a>Eigenschaftenzuordnungs-Makros

Diese Makros definieren eigenschaftenzuordnungen und Einträge.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|Markiert den Beginn der Zuordnung der ATL-Eigenschaft.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Gibt an, die Erweiterung, oder der Dimensionen eines ActiveX-Steuerelements.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Gibt eine Beschreibung, Eigenschaft DISPID und Eigenschaft Eigenschaftenseite CLSID in die eigenschaftenzuordnung an.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Gibt die Beschreibung einer Eigenschaft, DISPID, CLSID-Eigenschaftenseite-Eigenschaft und `IDispatch` IID in die eigenschaftenzuordnung.|
|[PROP_PAGE](#prop_page)|Gibt die CLSID auf einer Eigenschaftenseite in der eigenschaftenzuordnung an.|
|[END_PROP_MAP](#end_prop_map)|Markiert das Ende der Zuordnung der ATL-Eigenschaft.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP

Markiert den Beginn der eigenschaftenzuordnung des Objekts.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
[in] Gibt die Klasse, die die eigenschaftenzuordnung enthält.

### <a name="remarks"></a>Hinweise

Die eigenschaftenzuordnung speichert Eigenschaft DISPIDs, Eigenschaftenseite CLSIDs, die Beschreibung der Eigenschaften und `IDispatch` IIDs. Klassen [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), und [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)die eigenschaftenzuordnung abrufen, und legen Sie diese Informationen verwenden.

Wenn Sie ein Objekt mit dem ATL-Projekt-Assistenten erstellen, der Assistent erstellt eine Zuordnung für die Eigenschaft "empty" durch Angabe von BEGIN_PROP_MAP gefolgt von [END_PROP_MAP](#end_prop_map).

BEGIN_PROP_MAP werden Sie den Umfang (d. h. der Dimensionen) ein, der eine eigenschaftenzuordnung nicht gespeichert werden, da ein Objekt, das mithilfe einer eigenschaftenzuordnung eine Benutzeroberfläche, keine kann daher keine Block werden müssten. Wenn das Objekt ein ActiveX-Steuerelement mit einer Benutzeroberfläche ist, hat es einen Block den Wert an. In diesem Fall müssen Sie angeben [PROP_DATA_ENTRY](#prop_data_entry) in der Zuordnung des Wertebereichs angeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY

Gibt an, die Erweiterung, oder der Dimensionen eines ActiveX-Steuerelements.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Parameter

*szDesc*<br/>
[in] Beschreibung der Eigenschaft.

*member*<br/>
[in] Der Datenmember, die das Ausmaß enthält; z. B. `m_sizeExtent`.

*vt*<br/>
[in] Gibt den VARIANT-Datentyp der Eigenschaft an.

### <a name="remarks"></a>Hinweise

Dieses Makro bewirkt, dass den angegebene Datenmember beibehalten werden.

Wenn Sie ein ActiveX-Steuerelement erstellen, fügt der Assistent dieses Makro nach dem Eigenschaft-Map-Makro [BEGIN_PROP_MAP](#begin_prop_map) und vor dem Eigenschaft-Map-Makro [END_PROP_MAP](#end_prop_map).

### <a name="example"></a>Beispiel

Im folgenden Beispiel, das Ausmaß des Objekts (`m_sizeExtent`) wird persistent gespeichert wird.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE

Verwenden Sie dieses Makro, um eine Beschreibung, Eigenschaft DISPID und Eigenschaft Eigenschaftenseite CLSID in der objektzuordnung Eigenschaft einzugeben.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Parameter

*szDesc*<br/>
[in] Beschreibung der Eigenschaft.

*dispid*<br/>
[in] Der Eigenschaftenwert DISPID.

*clsid*<br/>
[in] Die CLSID der zugeordneten Seite. Verwenden Sie den Sonderwert CLSID_NULL für eine Eigenschaft, die nicht über eine Eigenschaftenseite des zugehörigen verfügt.

*vt*<br/>
[in] Der Typ der Eigenschaft.

### <a name="remarks"></a>Hinweise

Die Makros PROP_ENTRY wurde unsicher und veraltet. Es wurde mit PROP_ENTRY_TYPE ersetzt.

Die [BEGIN_PROP_MAP](#begin_prop_map) Makro markiert den Beginn der eigenschaftenzuordnung; die [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).

##  <a name="prop_entry_type_ex"></a>  "PROP_ENTRY_TYPE_EX"

Ähnlich wie [PROP_ENTRY_TYPE](#prop_entry_type), jedoch können Sie eine bestimmte IID angeben, wenn das Objekt mehrere duale Schnittstellen unterstützt.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Parameter

*szDesc*<br/>
[in] Beschreibung der Eigenschaft.

*dispid*<br/>
[in] Der Eigenschaftenwert DISPID.

*clsid*<br/>
[in] Die CLSID der zugeordneten Seite. Verwenden Sie den Sonderwert CLSID_NULL für eine Eigenschaft, die nicht über eine Eigenschaftenseite des zugehörigen verfügt.

*iidDispatch*<br/>
[in] Die IID der dualen Schnittstelle definieren die Eigenschaft.

*vt*<br/>
[in] Der Typ der Eigenschaft.

### <a name="remarks"></a>Hinweise

Das Makro PROP_ENTRY_EX wurde unsicher und veraltet. Es wurde mit "PROP_ENTRY_TYPE_EX" ersetzt.

Die [BEGIN_PROP_MAP](#begin_prop_map) Makro markiert den Beginn der eigenschaftenzuordnung; die [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.

### <a name="example"></a>Beispiel

Im folgende Beispiel gruppiert die Einträge für `IMyDual1` gefolgt von einem Eintrag für `IMyDual2`. Eine Gruppierung nach duale Schnittstelle wird die Leistung verbessert.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>  PROP_PAGE

Verwenden Sie dieses Makro, um eine Eigenschaftenseite CLSID in der objektzuordnung Eigenschaft eingeben.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
[in] Die CLSID einer Eigenschaftenseite.

### <a name="remarks"></a>Hinweise

PROP_PAGE ähnelt [PROP_ENTRY_TYPE](#prop_entry_type), aber eine Beschreibung der Eigenschaft oder die DISPID ist nicht erforderlich.

> [!NOTE]
>  Wenn Sie bereits eine CLSID mit PROP_ENTRY_TYPE eingegeben haben oder ["PROP_ENTRY_TYPE_EX"](#prop_entry_type_ex), Sie müssen keinen weiteren Eintrag mit PROP_PAGE vornehmen.

Die [BEGIN_PROP_MAP](#begin_prop_map) Makro markiert den Beginn der eigenschaftenzuordnung; die [END_PROP_MAP](#end_prop_map) Makro markiert das Ende.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>  END_PROP_MAP

Markiert das Ende der eigenschaftenzuordnung des Objekts.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Hinweise

Wenn Sie ein Objekt mit dem ATL-Projekt-Assistenten erstellen, der Assistent erstellt eine Zuordnung für die Eigenschaft "empty" durch Angabe [BEGIN_PROP_MAP](#begin_prop_map) END_PROP_MAP gefolgt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_PROP_MAP](#begin_prop_map).

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
