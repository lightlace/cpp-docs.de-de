---
title: Snap-in-Objektmakros
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: b75dd04bed4895d722939d1bf9c0a6dfff2126e0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292596"
---
# <a name="snap-in-object-macros"></a>Snap-in-Objektmakros

Diese Makros bieten Unterstützung für Erweiterungen von-Snap-in.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung für ein Objekt-Snap-In.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Markiert den Beginn der Symbolleiste Zuordnung für ein Objekt-Snap-In.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Markiert das Ende der Zuordnung-Snap-in-Erweiterung Daten-Klasse für ein Objekt-Snap-In.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Markiert das Ende der Zuordnung Symbolleiste für ein Objekt-Snap-In.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Erstellt einen Datenmember für die Datenklasse der Snap-In-Erweiterung.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Gibt eine Datenklasse-Snap-in-Erweiterung in die Map-Snap-in-Erweiterung Daten des Objekts-Snap-In.|
|[SNAPINMENUID](#snapinmenuid)|Deklariert die ID des Kontextmenüs, die vom Objekt-Snap-In verwendet.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Gibt eine Symbolleiste in der Symbolleiste Zuordnung des Snap-in-Objekts.|

## <a name="requirements"></a>Anforderungen

**Header:** atlsnap.h

##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Markiert den Beginn der Snap-In-Erweiterung Daten Klasse Zuordnung.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Parameter

*classname*<br/>
[in] Der Name der Datenklasse-Snap-in-Erweiterung.

### <a name="remarks"></a>Hinweise

Starten Sie die Zuordnung der Snap-In-Erweiterung mit dem Makro BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP, fügen Sie Einträge für jede der Datentypen-Snap-in-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Zuordnung mit der [ END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP

Deklariert den Anfang des der Symbolleisten-ID-Karte für das Snap-In-Objekt.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Parameter

*_class*<br/>
[in] Gibt die Objektklasse-Snap-In an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP

Markiert das Ende der Zuordnung-Snap-in-Erweiterung Daten-Klasse.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Hinweise

Starten Sie die Zuordnung der Snap-In-Erweiterung mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) Makro verwenden, fügen Sie Einträge für jede der Erweiterungs-Snap-in Datentypen mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) -Makro, und führen Sie die Zuordnung mit dem Makro END_EXTENSION_SNAPIN_NODEINFO_MAP.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP

Deklariert das Ende des der Symbolleisten-ID-Karte für das Snap-In-Objekt.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Parameter

*_class*<br/>
[in] Gibt die Objektklasse-Snap-In an.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS

Fügt einen Datenmember auf die Datenklasse der Snap-In-Erweiterung für eine **ISnapInItemImpl**-abgeleitete Klasse.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Parameter

*dataClass*<br/>
[in] Die Datenklasse der Snap-In-Erweiterung.

### <a name="remarks"></a>Hinweise

Diese Klasse sollte auch in einer Snap-In-Erweiterung Klasse datenzuordnung eingegeben werden. Starten Sie Ihre Karte-Snap-in-Erweiterung Daten-Klasse, mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) Makro verwenden, fügen Sie Einträge für jede der Datentypen-Snap-in-Erweiterung mit der [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)-Makro, und führen Sie die Zuordnung mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY

Die Map-Snap-in-Erweiterung Daten wird eine Datenklasse-Snap-in-Erweiterung hinzugefügt.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Parameter

*dataClass*<br/>
[in] Die Datenklasse der Snap-In-Erweiterung.

### <a name="remarks"></a>Hinweise

Starten Sie Ihre Karte-Snap-in-Erweiterung Daten-Klasse, mit der [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) Makro verwenden, fügen Sie Einträge für jeden der Datentypen mit dem Makro EXTENSION_SNAPIN_NODEINFO_ENTRY-Snap-in-Erweiterung hinzu, und schließen Sie die Zuordnung mit der [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) Makro.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

##  <a name="snapinmenuid"></a>  SNAPINMENUID

Verwenden Sie dieses Makro, um die Kontext-Menüressource des Objekts-Snap-In zu deklarieren.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Identifiziert das Kontextmenü des Snap-in-Objekts.

##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY

Verwenden Sie dieses Makro, um eine Symbolleisten-ID in der Snap-In-Objekt Symbolleisten-ID-Zuordnung einzugeben.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Identifiziert das Symbolleisten-Steuerelement.

### <a name="remarks"></a>Hinweise

Die [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) Makro markiert den Anfang des der Symbolleisten-ID-Karte und das [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) Makro markiert das Ende.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
