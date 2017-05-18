---
title: Connection Point Makros | Microsoft-Dokumentation
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
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: c16b6f2f889745270a51a32a1449add86dec6ecb
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-macros"></a>Connection Point-Makros
Diese Makros definieren Connection Point-Karten und Einträge.  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Markiert den Beginn von den Connection Point-Zuordnungseinträgen.|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Gibt ein Verbindungspunkte in der Zuordnung.|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) Ähnlich wie CONNECTION_POINT_ENTRY verwendet jedoch einen Zeiger auf die Iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Markiert das Ende der Verbindung Point-Zuordnungseinträgen.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen 
   
##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP  
 Markiert den Beginn von den Connection Point-Zuordnungseinträgen.  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name der Klasse, die die Verbindungspunkte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie Ihre Verbindung Point-Zuordnung mit der `BEGIN_CONNECTION_POINT_MAP` -Makro, fügen Sie Einträge für jede Ihrer Verbindungspunkte mit der [CONNECTION_POINT_ENTRY](#connection_point_entry) -Makro, und führen Sie die Karte mit der [END_CONNECTION_POINT_MAP](#end_connection_point_map) Makro.  
  
 Weitere Informationen zu den in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#101;](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY und CONNECTION_POINT_ENTRY_P  
 Gibt einen Verbindungspunkt für die angegebene Schnittstelle in der Verbindungstabelle zeigen, damit darauf zugegriffen werden kann.  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle der Verbindungstabelle Punkt hinzugefügt wird. 
 
 `piid`  
 [in] Ein Zeiger auf die GUID der Schnittstelle Adde wird.   
  
### <a name="remarks"></a>Hinweise  
 Connection Point-Einträge in der Zuordnung wird durch [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Die Klasse, die mit der Verbindung Punkt Zuordnung muss erben von `IConnectionPointContainerImpl`.  
  
 Starten Sie Ihre Verbindung Point-Zuordnung mit der [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) -Makro, fügen Sie Einträge für jede Ihrer Verbindungspunkte mit der `CONNECTION_POINT_ENTRY` -Makro, und führen Sie die Karte mit der [END_CONNECTION_POINT_MAP](#end_connection_point_map) Makro.  
  
 Weitere Informationen zu den in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#120;](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP  
 Markiert das Ende der Verbindung Point-Zuordnungseinträgen.  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie Ihre Verbindung Point-Zuordnung mit der [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) -Makro, fügen Sie Einträge für jede Ihrer Verbindungspunkte mit der [CONNECTION_POINT_ENTRY](#connection_point_entry) -Makro, und führen Sie die Karte mit der `END_CONNECTION_POINT_MAP` Makro.  
  
 Weitere Informationen zu den in ATL-Verbindungspunkte, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#128;](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Verbindungspunkt globale Funktionen](../../atl/reference/connection-point-global-functions.md)

