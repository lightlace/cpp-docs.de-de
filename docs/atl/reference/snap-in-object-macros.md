---
title: Snap-in-Makros | Microsoft-Dokumentation
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
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
caps.latest.revision: 16
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
ms.openlocfilehash: 13823feb06e7fecb2e81a01f3c88e3664de01d30
ms.lasthandoff: 02/24/2017

---
# <a name="snap-in-object-macros"></a>Snap-in-Makros
Diese Makros bieten Unterstützung für Snap-in-Erweiterungen.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung für ein Objekt-Snap-In.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Markiert den Beginn der Symbolleiste Zuordnung für ein Objekt-Snap-In.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Markiert das Ende der Snap-In-Erweiterung Daten Klasse Zuordnung für ein Objekt-Snap-In.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Markiert das Ende der Zuordnung Symbolleiste für ein Objekt-Snap-In.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Erstellt einen Datenmember für die Datenklasse der Snap-In-Erweiterung.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Gibt eine Datenklasse Snap-In-Erweiterung in der Snap-In-Erweiterung Daten Klasse Zuordnung des Objekts-Snap-In.|  
|[SNAPINMENUID](#snapinmenuid)|Deklariert die ID des Kontextmenüs der Snap-In-Objekt verwendet.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Gibt eine Symbolleiste in der Symbolleiste Zuordnung der Snap-In-Objekt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h 
   
##  <a name="a-namebeginextensionsnapinnodeinfomapa--beginextensionsnapinnodeinfomap"></a><a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 [in] Der Name der Datenklasse Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Zuordnung der Snap-In-Erweiterung mit der `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` -Makro, fügen Sie Einträge für jede Ihrer Datentypen Snap-In-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Karte mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="a-namebeginsnapintoolbaridmapa--beginsnapintoolbaridmap"></a><a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP  
 Deklariert den Beginn der Symbolleiste-ID-Zuordnung für das Snap-In-Objekt.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt die Objektklasse-Snap-In.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#106;](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="a-nameendextensionsnapinnodeinfomapa--endextensionsnapinnodeinfomap"></a><a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Markiert das Ende der Zuordnung Snap-In-Erweiterung Daten-Klasse.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Zuordnung der Snap-In-Erweiterung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für jede Ihrer Erweiterung Snap-in-Datentypen mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Karte mit der `END_EXTENSION_SNAPIN_NODEINFO_MAP` Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="a-nameendsnapintoolbaridmapa--endsnapintoolbaridmap"></a><a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP  
 Deklariert das Ende der Symbolleiste-ID-Zuordnung für das Snap-In-Objekt.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Parameter  
 `_class`  
 [in] Gibt die Objektklasse-Snap-In.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="a-nameextensionsnapindataclassa--extensionsnapindataclass"></a><a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS  
 Fügt einen Datenmember auf die Klasse des Snap-In-Erweiterung für eine **ISnapInItemImpl**-abgeleiteten Klasse.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Parameter  
 `dataClass`  
 [in] Die Datenklasse der Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse sollte auch in einer Snap-In-Erweiterung Daten Klasse Zuordnung eingegeben werden. Starten Sie die Snap-In-Erweiterung Klasse Zuordnung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für jede Ihrer Datentypen Snap-In-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Karte mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="a-nameextensionsnapinnodeinfoentrya--extensionsnapinnodeinfoentry"></a><a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Der Snap-In-Erweiterung Klasse Zuordnung hinzugefügt eine Datenklasse Snap-In-Erweiterung.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Parameter  
 `dataClass`  
 [in] Die Datenklasse der Snap-In-Erweiterung.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie die Snap-In-Erweiterung Klasse Zuordnung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) -Makro, fügen Sie Einträge für jede Ihrer Datentypen Snap-In-Erweiterung mit der `EXTENSION_SNAPIN_NODEINFO_ENTRY` -Makro, und führen Sie die Karte mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="a-namesnapinmenuida--snapinmenuid"></a><a name="snapinmenuid"></a>SNAPINMENUID  
 Verwenden Sie dieses Makro, um die Menüressource Kontext des Objekts-Snap-In zu deklarieren.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Kontextmenü des Objekts-Snap-In.  
  
##  <a name="a-namesnapintoolbaridentrya--snapintoolbaridentry"></a><a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY  
 Verwenden Sie dieses Makro eine Symbolleisten-ID in der Snap-In-Objekt Symbolleiste ID Zuordnung eingeben.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Identifiziert das Symbolleisten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) Makro kennzeichnet den Anfang der Symbolleisten-ID-Karte, die [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) Makro markiert das Ende.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

