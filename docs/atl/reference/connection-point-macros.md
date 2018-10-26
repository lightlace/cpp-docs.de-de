---
title: Verbindungspunkt-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a654f820d3c1dcdaa49ed8b3b3203d2c271b6880
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055480"
---
# <a name="connection-point-macros"></a>Verbindungspunkt-Makros

Diese Makros definieren Punkt verbindungszuordnungen und Einträge.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Markiert den Beginn der Zuordnungseintrags Punkt-Verbindung.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Gibt ein Verbindungspunkte in der Zuordnung.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) Ähnlich wie CONNECTION_POINT_ENTRY hat jedoch einen Zeiger auf die Iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Markiert das Ende der Zuordnungseintrags Punkt-Verbindung.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP

Markiert den Beginn der Zuordnungseintrags Punkt-Verbindung.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Klasse, die die Verbindungspunkte enthält.

### <a name="remarks"></a>Hinweise

Starten Sie Ihre Verbindung Point-Zuordnung mit dem Makro BEGIN_CONNECTION_POINT_MAP, fügen Sie Einträge für jede Ihrer Verbindungspunkte mit der [CONNECTION_POINT_ENTRY](#connection_point_entry) -Makro, und führen Sie die Zuordnung mit der [END_CONNECTION_ POINT_MAP](#end_connection_point_map) Makro.

Weitere Informationen zu in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY und CONNECTION_POINT_ENTRY_P

Gibt einen Verbindungspunkt für die angegebene Schnittstelle in die Zuordnung der Connection Point, damit darauf zugegriffen werden kann.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parameter

*IID*<br/>
[in] Die GUID der Schnittstelle, die zur Verbindung Punkt Karte hinzugefügt wird.

*piid*<br/>
[in] Zeiger auf die GUID der Schnittstelle Adde wird.

### <a name="remarks"></a>Hinweise

Connection Point-Einträge in der Zuordnung werden verwendet, indem [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Die Klasse, die mit der Verbindung Punkt Zuordnung erben muss `IConnectionPointContainerImpl`.

Starten Sie Ihre Verbindung Point-Karte mit den [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) Makro verwenden, fügen Sie Einträge für jede Ihrer Verbindungspunkte, mit dem Makro CONNECTION_POINT_ENTRY hinzu, und schließen Sie die Zuordnung mit der [END_CONNECTION_ POINT_MAP](#end_connection_point_map) Makro.

Weitere Informationen zu in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP

Markiert das Ende der Zuordnungseintrags Punkt-Verbindung.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Hinweise

Starten Sie Ihre Verbindung Point-Karte mit der [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) Makro verwenden, fügen Sie Einträge für jede Ihrer Verbindungspunkte mit der [CONNECTION_POINT_ENTRY](#connection_point_entry) -Makro, und führen Sie die Zuordnung mit der END_ CONNECTION_POINT_MAP-Makro.

Weitere Informationen zu in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[Globale Verbindungspunkt-Funktionen](../../atl/reference/connection-point-global-functions.md)
