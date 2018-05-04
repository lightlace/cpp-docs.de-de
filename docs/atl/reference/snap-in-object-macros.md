---
title: -Snap-In-Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
dev_langs:
- C++
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8a335bbe5424ca04f1db03a3f3ac4bf3cfa9ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="snap-in-object-macros"></a>Makros Snap-In-Objekt
Diese Makros bieten Unterstützung für Snap-in-Erweiterungen.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung für ein Snap-In-Objekt.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Markiert den Beginn der Symbolleiste Zuordnung für ein Snap-In-Objekt.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Markiert das Ende der Snap-In-Erweiterung Daten Klasse Zuordnung für ein Snap-In-Objekt.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Markiert das Ende der Zuordnung Symbolleiste für ein Snap-In-Objekt.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Erstellt einen Datenmember für die Datenklasse der Snap-In-Erweiterung.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Gibt eine Datenklasse Snap-In-Erweiterung in der Snap-In-Erweiterung Daten Klasse Zuordnung des Objekts-Snap-In.|  
|[SNAPINMENUID](#snapinmenuid)|Deklariert die ID des Kontextmenüs, die von dem Objekt-Snap-In verwendet.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Gibt eine Symbolleiste in der Symbolleiste Zuordnung des Objekts-Snap-In.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Parameter  
 *classname*  
 [in] Der Name der Datenklasse fest Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Zuordnung der Snap-In-Erweiterung mit der `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` -Makro, fügen Sie Einträge für die einzelnen Datentypen Snap-In-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Zuordnung mit der [END_ EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP  
 Deklariert den Anfang der Symbolleiste-ID-Zuordnung für das Snap-In-Objekt.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt die Objektklasse-Snap-In an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Markiert das Ende der Zuordnung Snap-In-Erweiterung Data-Klasse.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Zuordnung der Snap-In-Erweiterung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für jede Ihrer Erweiterungstypen-Snap-in-Daten mit den [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro und führen Sie die Zuordnung mit der `END_EXTENSION_SNAPIN_NODEINFO_MAP` Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP  
 Deklariert das Ende der Symbolleiste-ID-Zuordnung für das Snap-In-Objekt.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt die Objektklasse-Snap-In an.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS  
 Die Datenklasse Snap-In-Erweiterung für einen Datenmember hinzugefügt ein **ISnapInItemImpl**-Klasse.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Parameter  
 `dataClass`  
 [in] Die Datenklasse der Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse sollte auch in einer Snap-In-Erweiterung Klasse datenzuordnung eingegeben werden. Starten Sie die Snap-In-Erweiterung Daten Klasse Zuordnung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für die einzelnen Datentypen Snap-In-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)-Makro, und führen Sie die Zuordnung mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Der Snap-In-Erweiterung Daten Klasse Zuordnung hinzugefügt eine Datenklasse Snap-In-Erweiterung.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Parameter  
 `dataClass`  
 [in] Die Datenklasse der Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Snap-In-Erweiterung Daten Klasse Zuordnung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für die einzelnen Datentypen Snap-In-Erweiterung mit der `EXTENSION_SNAPIN_NODEINFO_ENTRY` -Makro, und führen Sie die Zuordnung mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>  SNAPINMENUID  
 Verwenden Sie dieses Makro, um die Menüressource Kontext des Objekts-Snap-In zu deklarieren.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Kontextmenü des Objekts-Snap-In.  
  
##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY  
 Verwenden Sie dieses Makro, um eine Symbolleiste-ID eingeben, in der Snap-In-Objekt Symbolleiste-ID-Zuordnung.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Symbolleisten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) Makro kennzeichnet den Anfang der Symbolleisten-ID-Zuordnung; das [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
